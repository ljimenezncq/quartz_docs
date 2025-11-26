## 1. Asignación de cod_impuesto por defecto `"IVA-00"`

**Coincidencia:** categoría `CR_Impuestos`  
**Archivo:** frmArticulosFacturaXML.cs  
**Línea aprox.:** 735–767  

### Contexto de código

```csharp
this.dtgArticuloNuevo.DataSource = pdtArticulosNuevos;

foreach (DataRow row in pdtArticulosNuevos.Rows)
{
    row["cod_articulo_proveedor"] = row["cod_articulo"].ToString().Trim();
    DataRow[] rows = null;
    try
    {
        rows = ((DataTable)repImpuesto.DataSource)
               .Select("codigo_tarifa_hacienda ='" + row["codigo_tarifa"] + "'");
    }
    catch { }
    if (rows != null)
    {
        if (rows.Length > 0)
        {
            row["cod_impuesto"] = rows[0]["cod_impuesto"];
        }
    }
    else
    {
        row["cod_impuesto"] = "IVA-00";
    }
}

if (pdtArticulosNuevos.Rows.Count > 0)
{
    this.tabArticulosNuevos.PageVisible = true;
}
else
{
    this.tabArticulosNuevos.PageVisible = false;
}
```

### ¿Qué está pasando?

- Se recorre el DataTable `pdtArticulosNuevos` con artículos nuevos detectados.
    
- Se intenta encontrar el impuesto correspondiente según `codigo_tarifa` en el `repImpuesto.DataSource`.
    
- Si se encuentra fila: se toma `rows[0]["cod_impuesto"]`.
    
- Si **no** hay filas (`rows == null`): se asigna **por defecto**  
    `row["cod_impuesto"] = "IVA-00";`.
    

### Riesgo / impacto para RD

- **"IVA-00" es un código de impuesto completamente CR-específico.**
    
- Para RD debería usarse algún código equivalente de **ITBIS**, basado en como definan el catálogo de impuestos en DGII.
    
- Este “fallback” es riesgoso porque:
    
    - Si la tarifa no matchea, en CR cae en un IVA genérico.
        
    - En RD esto podría disparar un ITBIS incorrecto o no permitido.
        
- Este bloque **no es despreciable**:
    
    - Requiere al menos:
        
        - Configurar el código por país (feature/localization).
            
        - O usar un catálogo de impuestos RD (equivalente a repImpuesto) con códigos adecuados.
            
        - O marcar el artículo como “impuesto no determinado” en vez de forzar un código fijo.
            

---

## 2. Copia de CABYS en la tabla “Nuevos” (estructura interna)
**Coincidencia:** categoría `CR_CABYS`  
**Archivo:** frmArticulosFacturaXML.cs  
**Línea aprox.:** 1311–1350

### Contexto de código

```csharp
/// <summary>
/// ASOMARRIBA_125
/// Metodo que agrega una nueva línea a la tabla de nuevos
/// </summary>
/// <param name="rowArticulo">Row con la información del artículo</param>
private void AgregarArticuloNuevo(DataRow rowArticulo)
{
    DataRow row = dsetArticulos.Tables["Nuevos"].NewRow();
    row["linea"] = rowArticulo["linea"];
    row["cod_articulo"] = rowArticulo["cod_articulo_factura"];
    row["descripcion"] = rowArticulo["desc_articulo_factura"];
    row["precio_default"] = rowArticulo["precio_default"];
    row["precio_unitario"] = rowArticulo["precio_unitario"];
    row["porcentaje_utilidad"] = "0";
    row["porcentaje_utilidad_sugerido"] = "0";
    row["porcentaje_f"] = rowArticulo["porcentaje_f"];
    row["MontoImpuesto"] = rowArticulo["MontoImpuesto"];
    row["Nuevo"] = "1";
    row["cod_proveedor"] = rowArticulo["cod_proveedor"];
    row["codigo_tarifa"] = rowArticulo["codigo_tarifa"];
    row["unidad_compra"] = rowArticulo["unidad_compra"];
    row["unidad_venta"] = rowArticulo["unidad_venta"];
    row["unidad_empaque"] = rowArticulo["unidad_empaque"];
    row["cabys"] = rowArticulo["cabys"];
    row["cod_articulo_proveedor"] = rowArticulo["cod_articulo_factura"];
    row["cod_familia"] = rowArticulo["cod_familia"];
    row["cod_marca"] = rowArticulo["cod_marca"];
    row["cod_impuesto"] = rowArticulo["cod_impuesto"];
    row["era_articulo_inactivo"] = "S";
    row["cod_articulo_inactivo"] = rowArticulo["cod_articulo"];
    dsetArticulos.Tables["Nuevos"].Rows.Add(row);
}
```

### ¿Qué está pasando?

- Método `AgregarArticuloNuevo` arma un nuevo `DataRow` en `dsetArticulos.Tables["Nuevos"]`.
    
- Copia muchos campos desde `rowArticulo`.
    
- Entre ellos, copia **directamente** el valor:
    
    - `row["cabys"] = rowArticulo["cabys"];`
        
- Es decir, el DataSet interno “Nuevos” ya está **diseñado con una columna CABYS** y la llena con el valor que viene del proceso anterior (donde se leyó CABYS del XML o de la BD).
    

### Riesgo / impacto para RD

- Esta línea en sí misma es simple, pero:
    
    - Confirma que el DataSet “Nuevos” está **estructuralmente acoplado** a CABYS.
        
    - Cualquier lógica posterior que lea esa columna (`Nuevos["cabys"]`) asume que trae un código CR.
        
- Para RD, el campo podría:
    
    - Mantenerse como “código de clasificación genérico” (renombrar semánticamente, no necesariamente físicamente).
        
    - O migrarse a otro nombre (campo nuevo) para evitar que ponga CABYS directamente.
        
- No es una coincidencia despreciable: es un punto claro donde el código de clasificación entra al pipeline de “artículos nuevos”.
    

---

## 3. Texto UI: label sobre inconsistencias en impuesto de ventas

**Coincidencia:** categoría `CR_Impuestos`  
**Archivo:** frmArticulosFacturaXML.designer.cs  
**Línea aprox.:** 1350–1362

### Contexto de código

```csharp
this.label2.TabIndex = 12;
this.label2.Text = "Es responsabilidad del usuario revisar y corregir esto de forma manual.";
// 
// label1
// 
this.label1.AutoSize = true;
this.label1.Font = new System.Drawing.Font("Microsoft Sans Serif", 8.25F,
    System.Drawing.FontStyle.Bold, System.Drawing.GraphicsUnit.Point, ((byte)(0)));
this.label1.Location = new System.Drawing.Point(5, 81);
this.label1.Margin = new System.Windows.Forms.Padding(3, 0, 3, 1);
this.label1.Name = "label1";
this.label1.Size = new System.Drawing.Size(440, 13);
this.label1.TabIndex = 11;
this.label1.Text = " Lista de artículos que presentan inconsistencias en el impuesto de ventas. ";
```

### ¿Qué está pasando?

- Texto de una etiqueta (`label1`) en la parte superior de un tab de la pantalla.
    
- Informa al usuario que la lista muestra artículos con inconsistencias en **el impuesto de ventas**.
    
- “Impuesto de ventas” es terminología de CR (antes y en contexto de IVA).
    

### Riesgo / impacto para RD

- **Puramente UI, pero 100% CR-específico en terminología**:
    
    - En RD se habla de **ITBIS** y tipo de comprobante (NCF/e-CF), no “impuesto de ventas”.
        
- Debe:
    
    - Moverse a recursos localizables (`.resx`) o usar tu motor de localización.
        
    - Cambiar el texto según país:
        
        - CR: “inconsistencias en el impuesto de ventas / IVA”
            
        - RD: “inconsistencias en el ITBIS” (o wording que acuerden).
            
- No es lógica de negocio, pero sí UX crítica para que el usuario de RD entienda de qué trata el tab.
    

---

## 4. Texto de pestaña: `"Inconsistencias en IVA"`

**Coincidencia:** categoría `CR_Impuestos`  
**Archivo:** frmArticulosFacturaXML.designer.cs  
**Línea aprox.:** 1763–1772

### Contexto de código

```csharp
this.repRazonComercialAsociacion.PopupWidth = 700;
this.repRazonComercialAsociacion.ValueMember = "cod_proveedor";
// 
// tabImpuesto
// 
this.tabImpuesto.Controls.Add(this.dtgImpuesto);
this.tabImpuesto.Name = "tabImpuesto";
this.tabImpuesto.Size = new System.Drawing.Size(1386, 405);
this.tabImpuesto.Text = "Inconsistencias en IVA";
// 
// dtgImpuesto
// 
this.dtgImpuesto.Dock = System.Windows.Forms.DockStyle.Fill;
this.dtgImpuesto.Location = new System.Drawing.Point(0, 0);
this.dtgImpuesto.LookAndFeel.SkinName = "Black";
this.dtgImpuesto.LookAndFeel.UseDefaultLookAndFeel = false;
this.dtgImpuesto.MainView = this.viewImpuesto;

```

### ¿Qué está pasando?

- Definición del tab `tabImpuesto` dentro de la UI del formulario.
    
- El texto de la pestaña se define como:
    
    - `"Inconsistencias en IVA"`
        
- Esta pestaña seguramente muestra el grid `dtgImpuesto` con artículos que tienen diferencias o problemas con el impuesto que vino en el XML vs lo que la base espera.
    

### Riesgo / impacto para RD

- Igual que el label anterior, esto es **texto UX** pero con terminología de CR:
    
    - **IVA** es el impuesto CR.
        
    - En RD se usa **ITBIS**.
        
- Además:
    
    - El nombre `tabImpuesto` puede quedarse igual (neutro).
        
    - Lo importante es que el `.Text` se localice:
        
        - CR: “Inconsistencias en IVA”
            
        - RD: “Inconsistencias en ITBIS”
            
- También conviene revisar que el contenido del tab (`dtgImpuesto`) no tenga columnas tituladas “IVA” duro en el `.designer` o `.resx`.
    

---



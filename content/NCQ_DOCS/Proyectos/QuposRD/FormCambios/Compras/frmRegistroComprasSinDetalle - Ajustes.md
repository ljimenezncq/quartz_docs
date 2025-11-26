## 1. Columna: “Subtotal s/IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmRegistroComprasSinDetalle.designer.cs  
**Línea aprox.:** 1738

### Contexto de código
```csharp
this.ColSubtotalIVA.Caption = "Subtotal s/IVA";
```
### ¿Qué está pasando?

En el grid principal del formulario se muestra una columna cuyo encabezado indica **“Subtotal s/IVA”**.  
La columna representa el subtotal de la compra **sin incluir el impuesto**, y esta línea sólo define el caption visible; el cálculo del subtotal viene desde el dataset o la consulta SQL.

---

## 2. Columna: “Subtotal s/IVA local”

**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmRegistroComprasSinDetalle.designer.cs  
**Línea aprox.:** 2273

### Contexto de código

```csharp
this.ColSubtotalIVALocal.Caption = "Subtotal s/IVA local";
```

### ¿Qué está pasando?

Aquí se configura otra columna que muestra el subtotal **sin impuesto**, pero expresado en **moneda local**.  
El texto “s/IVA local” es únicamente el encabezado de la columna; el valor ya está calculado en los datos que recibe el grid.

---

## 3. Columna: “Cédula”

**Coincidencia:** `Documento_Cedula`  
**Archivo:** frmRegistroComprasSinDetalle.designer.cs  
**Línea aprox.:** 1445

### Contexto de código

```csharp
this.colProveedorCedula.Caption = "Cédula";
```
`

### ¿Qué está pasando?

El formulario tiene una columna que muestra el **documento del proveedor**, y la etiqueta de la cabecera es “Cédula”.  
Esta línea sólo define el texto visible en la cabecera del grid para ese campo.

---

## 4. Campo de datos: “cedula”

**Coincidencia:** `Documento_Cedula`  
**Archivo:** frmRegistroComprasSinDetalle.designer.cs  
**Línea aprox.:** 1446

### Contexto de código

```csharp
this.colProveedorCedula.FieldName = "cedula";
```

### ¿Qué está pasando?

Se enlaza la columna visual del grid al campo de datos llamado **“cedula”** en el dataset o la consulta de compras.  
El sistema espera encontrar ese nombre de columna en los datos para cargar el documento del proveedor en la grilla.

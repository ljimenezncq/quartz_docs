## 1. Columna: “Cod. Cabys”

**Coincidencia:** `CR_CABYS`  
**Archivo:** frmConsultaDetalleCompraDinamico.designer.cs  
**Línea aprox.:** 3336  

### Contexto de código
```csharp
this.colCodCabys.Caption = "Cod. Cabys";
this.colCodCabys.FieldName = "cod_cabys";
```
### ¿Qué está pasando?

En el grid del detalle dinámico se muestra una columna cuyo caption y campo pertenecen al catálogo CABYS.  
Es un valor leído del dataset y mostrado tal cual; no hay cálculo alrededor.
---
## 2. Columna: “Subtotal s/IVA”

**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmConsultaDetalleCompraDinamico.designer.cs  
**Línea aprox.:** 1016

### Contexto de código
```csharp
this.pvtSubtotalIVA.Caption = "Subtotal s/IVA";
```

### ¿Qué está pasando?

Columna de una tabla dinámica que muestra el subtotal sin aplicar impuestos.  
El cálculo viene del dataset; aquí solo se asigna el texto “s/IVA”.

---

## 3. Columna: “Subtotal s/IVA” (grid principal)

**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmConsultaDetalleCompraDinamico.designer.cs  
**Línea aprox.:** 2297

### Contexto
```csharp
this.ColSubtotalIVA.Caption = "Subtotal s/IVA";
```

### ¿Qué está pasando?

En el grid principal, esta columna también muestra el subtotal sin impuestos.  
Es el mismo concepto mostrado en otra vista.

---

## 4. Columna detalle: “Subtotal s/IVA”

**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmConsultaDetalleCompraDinamico.designer.cs  
**Línea aprox.:** 5154

### Contexto
```csharp
this.ColSubtotalIVADetalle.Caption = "Subtotal s/IVA";
```

### ¿Qué está pasando?

Otra variante del mismo campo, en la vista detallada de las líneas de la compra.  
Solo asigna un caption para mostrar el subtotal antes del impuesto.

---

## 5. FieldName configurado como "Subtotal s/IVA"

**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmConsultaDetalleCompraDinamico.designer.cs  
**Línea aprox.:** 5156

### Contexto
```csharp
this.ColSubtotalIVADetalle.FieldName = "Subtotal s/IVA";
```

### ¿Qué está pasando?

Aquí el FieldName —que debería ser el nombre de la columna real del DataTable— quedó escrito como un caption.  
Es un error típico del diseñador (DevExpress) donde se mezcló nombre de campo con texto visual.

---

## 6. Columna: “Cédula”

**Coincidencia:** `Documento_Cedula`  
**Archivo:** frmConsultaDetalleCompraDinamico.designer.cs  
**Línea aprox.:** 3323–3324

### Contexto
```csharp
this.colCedula.Caption = "Cédula"; this.colCedula.FieldName = "cedula";
```

### ¿Qué está pasando?

En el detalle de compra se muestra un campo llamado “cedula”, traído directamente del dataset `detalle_compra`.  
El grid refleja ese valor como documento del proveedor.
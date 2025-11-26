
## 1. Texto: “Impuesto de ventas de importación:”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmDetalleCompraImportacion.Designer.cs  
**Línea aprox.:** 535

### Contexto de código
```csharp
this.labelControl4.Text = "Impuesto de ventas de importación:";
```

### ¿Qué está pasando?
Es la etiqueta asociada al campo numérico **spnImpuestoVentasImportacion**, que captura el impuesto aplicado a la importación según la factura.  
El texto usa la expresión “impuesto de ventas”, propia del esquema tributario de Costa Rica.  
La lógica detrás del campo sí se usa para cálculos del encabezado y ajuste de costos de importación.

---

## 2. Columna: “Impuesto de ventas”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmDetalleCompraImportacion.Designer.cs  
**Línea aprox.:** 838

### Contexto de código
```csharp
this.colImpuestoVentas.Caption = "Impuesto de ventas";
```

### ¿Qué está pasando?
Es una columna del grid de detalles de artículos que muestra el **monto total del impuesto** aplicado a cada línea importada.  
El cálculo viene del dataset (`monto_total_imp`), y esta línea únicamente asigna el caption visual usado en el grid.

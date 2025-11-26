
## 1. Coincidencia: Referencia CR (IVA / 13%)
**Archivo:** frmRegistroComprasSinDetalleEdicion.cs  
**Línea aprox.:** 786

### Fragmento de código
```csharp
//El porcentaje de impuesto de ventas que trae no se muestra ejemplo 13% pero si se salva
```

### ¿Qué está pasando?
Comentario interno del desarrollador que hace referencia al “impuesto de ventas” (IVA de Costa Rica, 13%).  
Describe que el porcentaje no se muestra visualmente, pero sí se conserva al guardar la compra.  
No ejecuta lógica, solo documenta comportamiento.

---

## 2. Coincidencia: Referencia CR (IVA / 13%)
**Archivo:** frmRegistroComprasSinDetalleEdicion.Designer.cs  
**Línea aprox.:** 1136

### Fragmento de código
```csharp
this.lblTotalImpuestoVentas.Text = "Total impuesto de ventas:";
```

### ¿Qué está pasando?
Esta línea define el texto estático del label asociado a `spnTotalImpuestoVentas`.  
El literal “impuesto de ventas” es propio del esquema tributario de Costa Rica.  
El control despliega el monto total del impuesto calculado para la compra.

---

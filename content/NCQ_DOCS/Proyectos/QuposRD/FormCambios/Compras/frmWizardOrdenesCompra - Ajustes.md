## 1. Coincidencia: Referencia CR (IVA / 13%)
**Archivo:** frmWizardOrdenesCompra.designer.cs  
**Línea aprox.:** 2664

### Fragmento de código
```csharp
this.ColTotalImpuestoPedido.Caption = "Total IVA";
```

### ¿Qué está pasando?
Esta línea define el **título de la columna** `ColTotalImpuestoPedido` dentro del grid del wizard de órdenes de compra.

El texto mostrado al usuario es **“Total IVA”**, que corresponde a la terminología tributaria de Costa Rica.  
La columna muestra el **monto total del impuesto aplicado al pedido**, según el cálculo realizado en el detalle de la orden.

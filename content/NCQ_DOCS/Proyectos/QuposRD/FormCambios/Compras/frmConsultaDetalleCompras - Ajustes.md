## 1. Columna: “Subtotal s/IVA”

**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmConsultaDetalleCompras.Designer.cs
**Línea aprox.:** 1440  

### Contexto de código
```csharp
this.ColSubtotalIVA.Caption = "Subtotal s/IVA";
```
### ¿Qué está pasando?

Es una columna del grid del formulario que muestra el **subtotal antes de aplicar impuestos**.

El cálculo del subtotal viene desde el DataSet (`ConsultaDetalleCompra`), y aquí únicamente se define el texto visual mostrado en la cabecera (“s/IVA”).  
No se realiza ningún cálculo de IVA en este fragmento; es puramente un caption UI.
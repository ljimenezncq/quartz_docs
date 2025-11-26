## 1. Comentario sobre uso del impuesto de ventas

**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmDetalleCompra.cs  
**Línea aprox.:** 2339

### Contexto de código
```csharp
//Se utiliza el impuesto de ventas si es bonificado o si el campo de impuesto esta vacío
```

### ¿Qué está pasando?
En esta sección del código hay un comentario que explica la lógica aplicada para determinar qué impuesto usar:  
cuando el artículo está marcado como bonificado, o cuando el campo del impuesto no tiene un valor asignado, el sistema usa el **impuesto de ventas**.

El comentario no ejecuta ninguna instrucción, pero documenta cómo la lógica está pensada con el esquema tributario de Costa Rica.
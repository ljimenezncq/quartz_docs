## 1. Texto del botón: “S/C IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmOrdenesCompraEdicion.Designer.cs  
**Línea aprox.:** 3882

### Contexto de código
```csharp
this.btnSCImpuesto.Text = "S/C IVA";
```

### ¿Qué está pasando?
En la barra de herramientas del formulario de edición de órdenes de compra existe un botón que muestra el texto **“S/C IVA”**.  
Este botón se utiliza para indicar que se está trabajando con líneas sin impuesto o con una condición especial respecto al impuesto.

---

## 2. Tooltip del botón sobre IVA en bonificaciones
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmOrdenesCompraEdicion.Designer.cs  
**Línea aprox.:** 3884

### Contexto de código
```csharp
this.btnSCImpuesto.ToolTipText = "Asigna o quita la tarifa del IVA para las líneas de tipo bonificación";
```

### ¿Qué está pasando?
Al pasar el mouse sobre el mismo botón, se muestra un mensaje que explica que su función es **asignar o quitar la tarifa de impuesto** a las líneas marcadas como bonificación dentro de la orden de compra.

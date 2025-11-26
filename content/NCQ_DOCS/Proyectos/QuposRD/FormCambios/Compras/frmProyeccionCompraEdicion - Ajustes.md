
## 1. Columna: “Costo última compra s/IVA”

**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmProyeccionCompraEdicion.designer.cs  
**Línea aprox.:** 2222

### Contexto de código
```csharp
this.colCostoUltimaCompraSinIVA.Caption = "Costo última compra s/IVA";
```

### ¿Qué está pasando?
El formulario muestra una columna que expresa el costo de la última compra **sin impuestos**.  
El texto “s/IVA” es un caption típico del modelo costarricense.  
Aquí solo se define el encabezado visual; la lógica del cálculo no depende directamente del IVA.

---

## 2. Columna: “Costo última compra c/IVA”

**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmProyeccionCompraEdicion.designer.cs  
**Línea aprox.:** 2238

### Contexto de código
```csharp
this.colCostoUltimaCompraConIVA.Caption = "Costo última compra c/IVA";
```

### ¿Qué está pasando?
El formulario muestra una columna que refleja el costo de la última compra **incluyendo el impuesto**.  
El texto “c/IVA” es únicamente un caption visual.  
El cálculo del costo ya está hecho en el dataset; aquí solo se asigna el texto al encabezado de la columna.

## 1. Texto de pestaña: “Detalle de tarifas IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmNotaCreditoCompra.Designer.cs  
**Línea aprox.:** 1336

### Contexto de código
```csharp
this.TabTarifas.Text = "Detalle de tarifas IVA";
```

### ¿Qué está pasando?
El tab controla una sección donde se listan las tarifas del impuesto aplicadas a la nota de crédito.  
El texto identifica la sección como relacionada a tarifas de impuesto.

---

## 2. Columna: “Tarifa IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmNotaCreditoCompra.Designer.cs  
**Línea aprox.:** 1480

### Contexto de código
```csharp
this.ColTarifa.Caption = "Tarifa IVA";
```

### ¿Qué está pasando?
El grid incluye una columna para mostrar el porcentaje del impuesto aplicado a cada línea de la nota de crédito.  
El caption solo etiqueta visualmente el campo.

---

## 3. Columna: “Total IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmNotaCreditoCompra.Designer.cs  
**Línea aprox.:** 1599

### Contexto de código
```csharp
this.ColTotalIVA.Caption = "Total IVA";
```

### ¿Qué está pasando?
Se muestra el monto total del impuesto cargado para cada detalle o para el consolidado de la nota.  
El valor proviene del dataset y aquí solo se configura el texto del encabezado.

---

## 4. Columna: “Subtotal c/IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmNotaCreditoCompra.Designer.cs  
**Línea aprox.:** 1618

### Contexto de código
```csharp
this.ColSubtotalConIVA.Caption = "Subtotal c/IVA";
```

### ¿Qué está pasando?
Es una columna que indica el subtotal incluyendo el impuesto.  
El cálculo del subtotal ya viene definido en la consulta y aquí solo se asigna el caption.

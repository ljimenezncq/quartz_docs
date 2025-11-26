
## 1. Columna: “Total sin IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmConsultaNotaCredito.Designer.cs  
**Línea aprox.:** 1327

### Contexto de código
```csharp
this.ColTotalSinImp.Caption = "Total sin IVA";
```

### ¿Qué está pasando?
El grid muestra una columna que representa el total antes de impuestos.  
El cálculo del total ya viene desde el dataset; aquí solo se asigna el caption “sin IVA”.

---

## 2. Columna: “Tarifa IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmConsultaNotaCredito.Designer.cs  
**Línea aprox.:** 1844

### Contexto de código
```csharp
this.ColTarifa.Caption = "Tarifa IVA";
```

### ¿Qué está pasando?
Se muestra la tarifa del impuesto aplicada a cada línea.  
El texto es solo un caption UI.

---

## 3. Columna: “Total IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmConsultaNotaCredito.Designer.cs  
**Línea aprox.:** 1963

### Contexto de código
```csharp
this.ColTotalIVA.Caption = "Total IVA";
```

### ¿Qué está pasando?
Columna que muestra el monto total del impuesto asociado.  
El valor viene precalculado desde la consulta; aquí solo se define la etiqueta visual.

---

## 4. Columna: “Subtotal c/IVA”
**Coincidencia:** `CR_Impuestos`  
**Archivo:** frmConsultaNotaCredito.Designer.cs  
**Línea aprox.:** 1982

### Contexto de código
```csharp
this.ColSubtotalConIVA.Caption = "Subtotal c/IVA";
```

### ¿Qué está pasando?
El grid presenta una columna con el subtotal incluyendo el impuesto.  
Solo define el texto visual.

---

## 5. Método: ValidarProveedor(string cedula)
**Coincidencia:** `Documento_Cedula`  
**Archivo:** frmConsultaNotaCredito.cs  
**Línea aprox.:** 1019

### Contexto
```csharp
internal string ValidarProveedor(string cedula)
```

### ¿Qué está pasando?
El método recibe un parámetro “cedula” y lo usa como identificador para buscar al proveedor.

---

## 6. Consulta a proveedores usando “cedula”
**Coincidencia:** `Documento_Cedula`  
**Archivo:** frmConsultaNotaCredito.cs  
**Línea aprox.:** 1023

### Contexto
```csharp
dsetDatos = oProveedor.ConsultaProveedores("", "", "", "", "", cedula);
```

### ¿Qué está pasando?
Se consulta el proveedor usando “cedula” como criterio.  
El sistema espera que la identificación se encuentre en ese campo.

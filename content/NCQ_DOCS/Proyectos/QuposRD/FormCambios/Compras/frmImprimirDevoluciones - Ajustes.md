
## 1. Línea impresa: “CÉDULA: …”
**Coincidencia:** `Documento_Cedula`  
**Archivo:** frmImprimirDevoluciones.cs  
**Línea aprox.:** 306

### Contexto de código
```csharp
print.agregarLinea("CÉDULA: " + dsetDatos.Tables[0].Rows[0]["identificacion"].ToString()+"\r\n", centro, normal, true);
```

### ¿Qué está pasando?
Durante la impresión del tiquete de devolución, se genera una línea que imprime la identificación del proveedor bajo el encabezado **“CÉDULA:”**.  
El sistema asume que el proveedor es una persona física y que el valor proviene del campo `identificacion` del dataset.

---

## 2. Línea impresa: “CÉDULA JURÍDICA: …”
**Coincidencia:** `Documento_Cedula`  
**Archivo:** frmImprimirDevoluciones.cs  
**Línea aprox.:** 308

### Contexto de código
```csharp
print.agregarLinea("CÉDULA JURÍDICA: " + dsetDatos.Tables[0].Rows[0]["identificacion"].ToString() + "\r\n", centro, normal, true);
```

### ¿Qué está pasando?
Cuando el tipo de identificación corresponde a una empresa, el sistema imprime la etiqueta **“CÉDULA JURÍDICA:”** seguida del mismo campo `identificacion`.  
La lógica se basa en el modelo costarricense (F/J) para diferenciar personas físicas y jurídicas.
# **1. ¿Qué es un Comprobante Fiscal Electrónico (e-CF)?**

El **Comprobante Fiscal Electrónico (e-CF)** es un documento fiscal digital que posee la misma validez legal que un comprobante físico tradicional. Se caracteriza por:

- Mantener un **formato estándar XML**, regulado por la DGII.
    
- Ser **emitido, firmado y transmitido electrónicamente**.
    
- Garantizar mayor **seguridad, integridad y trazabilidad** de la información.
    
- Cumplir con todas las especificaciones dispuestas en:
    
    - Decreto 254-06
        
    - Norma 06-18
        
    - Norma 05-19
        

Cada e-CF posee una **estructura compuesta por:**

### **Estructura del e-CF**

- **Serie:** Letra inicial que identifica el tipo de comprobante.
    
- **Secuencial:** Número consecutivo asignado por el sistema.
    

Ejemplo:  
`E31-00000000005`

- **E** → Indica comprobante electrónico
    
- **31** → Tipo (Factura Crédito Fiscal Electrónica)
    
- **0000000005** → Secuencial
    

---

# **2. Estados de Validación del e-CF**

Durante la transmisión a la DGII, el e-CF puede recibir tres tipos de respuestas:

### **2.1. Aceptado**

Indica que el formato del comprobante cumple con todas las especificaciones técnicas y ha sido **admitido por DGII**.

### **2.2. Rechazado**

Indica que el comprobante **no cumple** con las especificaciones, por lo que **no es recibido** por DGII.  
El emisor debe corregir **y reenviar** el archivo.

### **2.3. Aceptado Condicional**

El comprobante cumple con lo esencial, **pero presenta irregularidades menores** que deben corregirse para futuras remisiones.

---

# **3. Tipos de Comprobantes Fiscales Electrónicos (e-CF)**

La DGII establece distintos tipos de e-CF, según su propósito fiscal y comercial.

### **Listado oficial:**

|Código|Tipo de e-CF|
|---|---|
|**31**|Factura de Crédito Fiscal Electrónica|
|**32**|Factura de Consumo Electrónica|
|**33**|Nota de Débito Electrónica|
|**34**|Nota de Crédito Electrónica|
|**41**|Comprobante Electrónico de Compras|
|**43**|Comprobante Electrónico para Gastos Menores|
|**44**|Comprobante Electrónico para Regímenes Especiales|
|**45**|Comprobante Electrónico Gubernamental|
|**46**|Comprobante Electrónico para Exportaciones|
|**47**|Comprobante Electrónico para Pagos al Exterior|

---

# **4. Descripción técnica de cada tipo de e-CF**

### **4.1. Factura de Crédito Fiscal Electrónica (e-NCF 31)**

Registra ventas de bienes o servicios con derecho a **crédito fiscal, costos y gastos** para sustento tributario.

### **4.2. Factura de Consumo Electrónica (e-NCF 32)**

Utilizada para operaciones con **consumidores finales**.  
No genera crédito fiscal.

### **4.3. Nota de Débito Electrónica (e-NCF 33)**

Emitida para recuperar gastos posteriores a una factura:

- Mora
    
- Fletes
    
- Ajustes por costos adicionales
    

### **4.4. Nota de Crédito Electrónica (e-NCF 34)**

Utilizada para modificar o anular operaciones por:

- Devoluciones
    
- Descuentos
    
- Bonificaciones
    
- Corrección de errores
    

### **4.5. Comprobante Electrónico de Compras (e-NCF 41)**

Usado para registrar **compras a proveedores no registrados**.

### **4.6. Comprobante Electrónico para Gastos Menores (e-NCF 43)**

Sustenta gastos relacionados al trabajo, como:

- Peajes
    
- Pasajes
    
- Consumibles
    
- Transporte público
    

### **4.7. Comprobante Electrónico para Regímenes Especiales (e-NCF 44)**

Para operaciones **exentas de ITBIS/ISC**, según leyes o contratos especiales.

### **4.8. Comprobante Electrónico Gubernamental (e-NCF 45)**

Facturación dirigida a entidades gubernamentales **sin actividad comercial**.

### **4.9. Comprobante Electrónico para Exportaciones (e-NCF 46)**

Reporta ventas **fuera del país**, usado por:

- Exportadores
    
- Zonas francas industriales
    
- Zonas francas comerciales
    

### **4.10. Comprobante Electrónico para Pagos al Exterior (e-NCF 47)**

Para pagos de **rentas gravadas** a proveedores no residentes.  
Incluye retenciones de ISR según los artículos **297 y 305 del Código Tributario**.

---

# **5. Uso de los Comprobantes Fiscales Electrónicos**

## **5.1. Según tipo de cliente**

|Cliente|Comprobante a Utilizar|
|---|---|
|**Contribuyentes (PF o PJ)**|Factura de Crédito Fiscal|
|**Consumidores finales**|Factura de Consumo|

### Notas relacionadas:

Cualquier variación posterior debe justificarse con:

- **Nota de Crédito**
    
- **Nota de Débito**
    

---

# **6. Uso de Comprobantes Fiscales Especiales**

|Cliente|Comprobante|
|---|---|
|Gobierno, instituciones autónomas, SS, otros entes sin actividad comercial|Gubernamental|
|Personas físicas/jurídicas en regímenes especiales|Regímenes Especiales|

Otros usos:

- Pagos al exterior
    
- Exportaciones
    
- Compras a proveedores no registrados
    

---

# **7. Vencimiento de las Secuencias de NCF**

- Las secuencias de NCF asignadas tienen una validez de **dos años calendario**.
    
- Excepción: **Facturas de Consumo y Notas de Crédito**, que no se rigen por este plazo.
    

Ejemplo:  
Si se autoriza una secuencia en **julio 2018**, será válida hasta **31 de diciembre de 2019**.

---

# **8. Factura Física vs. Factura Electrónica**

### **Factura Física**

- Impresa en papel
    
- Incluye datos fiscales y código de seguridad
    

### **Factura Electrónica**

- Formato digital XML
    
- Incluye:
    
    - Código QR
        
    - Firma Digital
        
    - Campos obligatorios según tipo de e-CF
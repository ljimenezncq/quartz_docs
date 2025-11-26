Los contribuyentes son todas las personas o empresas que realizan actividades económicas que generan obligaciones tributarias.

### **Tipos de Contribuyentes**

Existen dos tipos principales:

### **1. Personas Físicas o Naturales**

Son individuos que realizan actividades económicas por cuenta propia o como trabajadores independientes.

### **2. Personas Jurídicas o Sociedades**

Son organizaciones o empresas formadas por una o varias personas con capacidad legal para realizar actividades comerciales.

---

# **Modelo Emisor–Receptor Electrónico (e-CF)**

El proceso funciona de la siguiente manera:

1. **El emisor electrónico envía el e-CF a la DGII** en el momento de su emisión.
    
2. **La DGII responde con un trackId**, que el emisor puede usar para consultar el estado del documento mediante el Web Service.
    
3. **El emisor envía el e-CF al receptor electrónico** después de recibir el trackId.
    
4. **El receptor electrónico acusa recibo del e-CF** al emisor.
    
5. **El receptor puede emitir una respuesta comercial**, ya sea Aprobación o Rechazo Comercial.
    
6. **La DGII es notificada** cuando el receptor envía su respuesta al emisor.
    

### **Pasos obligatorios:** 1–4

### **Pasos opcionales:** 5–6

---

# **Modelo Emisor Electrónico – Receptor No Electrónico**

Este modelo aplica cuando el emisor está autorizado como electrónico, pero el receptor no lo está.

El proceso es el siguiente:

1. **El emisor envía el e-CF a la DGII** al momento de la emisión.
    
2. **La DGII responde con un trackId**, utilizable para consultar el estado vía Web Service.
    
3. **El emisor entrega una Representación Impresa (RI)** del e-CF al receptor no electrónico.
    

### **Pasos obligatorios:** 1–3

---

# **Modelo de Factura de Consumo Electrónica (Consumidor Final)**

Este flujo se utiliza para la **Factura de Consumo Electrónica**, comúnmente usada en ventas al consumidor final.

1. **El emisor genera y guarda la Factura de Consumo Electrónica** en su sistema.
    
2. **Se envía el resumen de la factura al Web Service de la DGII**, el cual devuelve una respuesta de validación.
    
3. **La DGII valida la información** y confirma el estatus del documento.
    
4. **El emisor entrega la Representación Impresa** de la factura al receptor no electrónico (cliente final).
    

### **Aplicación:** ventas a clientes sin recepción electrónica.
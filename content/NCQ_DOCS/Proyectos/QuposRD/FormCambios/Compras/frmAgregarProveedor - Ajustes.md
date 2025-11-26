## 1. Label: “Tipo de cédula:”

**Coincidencia:** categoría `Documento_Cedula`  
**Archivo:** frmAgregarProveedor.designer.cs :contentReference[oaicite:2]{index=2}  
**Línea aprox.:** 405–412  

### Contexto de código

```csharp
// label2
this.label2.Location = new System.Drawing.Point(11, 31);
this.label2.Margin = new System.Windows.Forms.Padding(3, 0, 3, 1);
this.label2.Name = "label2";
this.label2.Size = new System.Drawing.Size(73, 13);
this.label2.TabIndex = 148;
this.label2.Text = "Tipo de cédula:";
```
### ¿Qué está pasando?

- Es un **LabelControl** dentro del grupo “Identificación”.
    
- Pertenece al formulario para agregar proveedores.
    
- Acompaña al **RadioGroup** `rdoTipoCedula`, que tiene dos opciones:
    
    - Física
        
    - Jurídica
        

### Contexto funcional más amplio

El código del RadioGroup se encuentra más adelante en el archivo principal del formulario:

```csharp
this.rdoTipoCedula.Properties.Items.AddRange(new RadioGroupItem[] {
    new RadioGroupItem("F", "Física"),
    new RadioGroupItem("J", "Jurídica")
});
```

Y este valor luego determina cómo se manejan ciertos campos:

```csharp
if (rdoTipoCedula.EditValue.ToString() == "Física")
{
    // RazonSocial read-only
    edtRazonSocial.Properties.ReadOnly = true;
}
else
{
    edtRazonSocial.Properties.ReadOnly = false;
}
```

### Impacto / Riesgo para RD

- En **Costa Rica**, “cédula física” y “cédula jurídica” son conceptos del Registro Civil / Tributación.
    
- En **República Dominicana**, la estructura es distinta:
    
    - Persona física → **Cédula**
        
    - Persona jurídica → **RNC**
        
    - Además existe **Cédula jurídica** pero su uso es diferente.
        

Este Label define explícitamente que la UI está pensada para el modelo de identificación de Costa Rica.

### Recomendación

- Debe volverse un **texto localizado** vía `.resx` o motor de localización.
    
- En RD probablemente debe decir:
    
    - “Tipo de documento”
        
    - Y el RadioGroup debería tener opciones diferentes:
        
        - “Cédula”
            
        - “RNC”
            
- También revisar la lógica del método `btnAgregar_Click`, donde el valor `rdoTipoCedula.EditValue` se envía directamente al constructor de `Proveedor.insertar`:
    

```csharp
oProveedor.insertar(..., rdoTipoCedula.EditValue.ToString(), edtCedula.Text, ...)
```

Esto podría requerir normalización por país.

---

## 2. Label: “Cédula:”

**Coincidencia:** categoría `Documento_Cedula`  
**Archivo:** frmAgregarProveedor.designer.cs  
**Línea aprox.:** 424–432

### Contexto de código

```csharp
// label1
this.label1.Location = new System.Drawing.Point(319, 31);
this.label1.Margin = new System.Windows.Forms.Padding(3, 0, 3, 1);
this.label1.Name = "label1";
this.label1.Size = new System.Drawing.Size(37, 13);
this.label1.TabIndex = 147;
this.label1.Text = "Cédula:";
```

### ¿Qué está pasando?

- Este es el **label asociado al campo edtCedula**, el cual captura el documento de identificación del proveedor.
    
- Es parte del mismo `GroupControl` “Identificación”.
    

El campo correspondiente:

```csharp
this.edtCedula.Properties.MaxLength = 100;
this.Validacion.SetValidationRule(this.edtCedula, conditionValidationRule5);
```

### Impacto / Riesgo para RD

- “Cédula” como único campo no es suficiente para RD.
    
- Los proveedores en República Dominicana pueden usar:
    
    - **Cédula**
        
    - **RNC**
        
    - **Pasaporte**
        
- Si mantienes este formulario en RD:
    
    - El label “Cédula:” debe cambiar a algo más genérico:  
        **“Documento:”**
        
    - O debe adaptarse según la selección del tipo (Física/Jurídica) o el tipo de documento del país.
        
- También hay que validar si la lógica de `Validacion` soporta formatos distintos.
    

### Recomendación

- Convertir el label a texto localizado.
    
- Integrar validaciones específicas según país:
    
    - CR → Cédulas físicas/jurídicas (números con guiones)
        
    - RD → Cédula / RNC (ambos con formatos específicos)
        
- Eventualmente el campo podría llamarse `edtDocumento` o delegarse a una clase de validación por país.
    

---
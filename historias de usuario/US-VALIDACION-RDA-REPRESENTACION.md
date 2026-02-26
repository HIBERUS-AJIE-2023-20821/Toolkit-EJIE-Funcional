# US-XXX: Validación de representación vigente en RDA para representación voluntaria

## Historia de usuario
**Como** aplicación  
**Quiero** comprobar si el DNI/CIF introducido en una representación voluntaria tiene representación vigente en el RDA  
**Para** permitir o bloquear el avance del solicitante según el resultado de la consulta

## Descripción funcional
Cuando el ciudadano inicia una solicitud **"Para Otros"** actuando como representante de un tercero mediante **representación voluntaria** (es decir, sin usar el RDA como mecanismo de representación), la aplicación debe consultar el Registro de Apoderamientos (RDA) para verificar que la persona representada no tiene ya una representación vigente registrada.

Si existe una representación vigente en el RDA para el DNI/CIF introducido, la solicitud no puede continuar mediante representación voluntaria, ya que el mecanismo a utilizar debe ser el RDA.

**Momento de la validación**: La comprobación se realiza al introducir el DNI/CIF de la persona representada en el paso de identificación de interesados.

**Resultado de la validación**:
- **Sin representación vigente en RDA**: Se permite continuar con la tramitación en modo representación voluntaria
- **Con representación vigente en RDA**: Se bloquea el avance y se muestra mensaje de error

## Criterios de aceptación

### CA-1: Consulta al RDA al introducir DNI/CIF del representado
**Dado** que el ciudadano está tramitando "Para Otros" con representación voluntaria  
**Cuando** introduce el DNI/CIF de la persona representada  
**Entonces** la aplicación consulta el RDA para verificar si existe representación vigente para ese identificador

### CA-2: Continuación cuando no existe representación vigente en RDA
**Dado** que la aplicación ha consultado el RDA con el DNI/CIF del representado  
**Cuando** el RDA no devuelve ninguna representación vigente para ese identificador  
**Entonces** la aplicación permite continuar con la tramitación en modo representación voluntaria

### CA-3: Bloqueo cuando existe representación vigente en RDA
**Dado** que la aplicación ha consultado el RDA con el DNI/CIF del representado  
**Cuando** el RDA devuelve que existe una representación vigente para ese identificador  
**Entonces** la aplicación bloquea el avance  
**Y** muestra un mensaje de error indicando que ya existe una representación vigente en el RDA para dicha identificación

### CA-4: Mensaje de error informativo
**Dado** que se ha detectado representación vigente en el RDA  
**Cuando** se muestra el mensaje de error  
**Entonces** el mensaje indica claramente que no es posible continuar con representación voluntaria  
**Y** el ciudadano no puede avanzar al siguiente paso sin corregir la situación

### CA-5: Validación solo para representación voluntaria
**Dado** que el ciudadano tramita "Para Otros"  
**Cuando** utiliza el RDA como mecanismo de representación  
**Entonces** no se realiza esta validación adicional  
**Y** la comprobación aplica exclusivamente al flujo de representación voluntaria

---

*Historia creada: 25/02/2026*

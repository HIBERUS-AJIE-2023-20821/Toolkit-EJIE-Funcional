# US-XXX: Visualización condicional del bloque LOPD según configuración RAT

**Épica:** [PENDIENTE DE ASIGNAR]

## Historia de usuario
**Como** ciudadano que inicia una tramitación  
**Quiero** visualizar únicamente la información de protección de datos cuando sea aplicable al procedimiento  
**Para** recibir información legal pertinente sin visualizar bloques innecesarios cuando el procedimiento no requiere tratamiento de datos especiales

## Descripción funcional
El bloque LOPD (Ley Orgánica de Protección de Datos) muestra los textos informativos correspondientes a los códigos RAT (Registro de Actividades de Tratamiento) configurados en el CCP para cada procedimiento administrativo.

**Configuración en CCP**: Cada procedimiento puede tener asociados uno o varios códigos RAT que identifican las actividades de tratamiento de datos personales que se realizarán durante la tramitación.

**Visualización condicional**: El sistema debe evaluar la configuración del procedimiento al que se ha accedido:
- **Si el procedimiento TIENE códigos RAT configurados**: El bloque LOPD se muestra en las pantallas correspondientes con los textos asociados a dichos códigos
- **Si el procedimiento NO TIENE códigos RAT configurados**: El bloque LOPD no debe aparecer en ningún punto de la aplicación

**Ubicaciones donde aplica la visualización condicional**:
1. **Paso Inicial**: Pantalla de inicio de la tramitación donde se presenta información general
2. **Resumen**: Pantalla de resumen previo al envío de la solicitud
3. **PDF/HTML de la solicitud**: Documento justificante generado tras la presentación

El sistema debe realizar esta evaluación de forma dinámica en el momento de acceso al procedimiento, consultando la configuración vigente en el CCP.

## Criterios de aceptación

### CA-1: Consulta de configuración RAT en CCP
**Dado** que el ciudadano accede a un procedimiento administrativo  
**Cuando** el sistema carga la configuración del procedimiento desde el CCP  
**Entonces** debe obtener la lista de códigos RAT asociados al procedimiento  
**Y** debe registrar si existen o no códigos RAT configurados

### CA-2: Visualización del bloque LOPD con códigos RAT configurados
**Dado** que el procedimiento tiene uno o más códigos RAT configurados en el CCP  
**Cuando** el ciudadano accede al Paso Inicial, Resumen o PDF/HTML de solicitud  
**Entonces** el sistema debe mostrar el bloque LOPD  
**Y** debe presentar los textos informativos correspondientes a los códigos RAT configurados  
**Y** el bloque debe ser claramente identificable como información de protección de datos

### CA-3: Ocultación del bloque LOPD sin códigos RAT - Paso Inicial
**Dado** que el procedimiento NO tiene códigos RAT configurados en el CCP  
**Cuando** el ciudadano accede al Paso Inicial  
**Entonces** el sistema NO debe mostrar el bloque LOPD  
**Y** no debe dejar espacio vacío ni indicación de bloque oculto

### CA-4: Ocultación del bloque LOPD sin códigos RAT - Resumen
**Dado** que el procedimiento NO tiene códigos RAT configurados en el CCP  
**Cuando** el ciudadano accede a la pantalla de Resumen  
**Entonces** el sistema NO debe mostrar el bloque LOPD  
**Y** no debe incluir ninguna referencia a protección de datos en el resumen

### CA-5: Ocultación del bloque LOPD sin códigos RAT - PDF/HTML
**Dado** que el procedimiento NO tiene códigos RAT configurados en el CCP  
**Cuando** el sistema genera el PDF o HTML de la solicitud  
**Entonces** el documento NO debe incluir el bloque LOPD  
**Y** el documento debe generarse correctamente sin secciones vacías relacionadas con LOPD

### CA-6: Múltiples códigos RAT
**Dado** que el procedimiento tiene varios códigos RAT configurados en el CCP  
**Cuando** el sistema muestra el bloque LOPD  
**Entonces** debe presentar los textos de TODOS los códigos RAT configurados  
**Y** debe mantener el orden o agrupación según configuración del CCP  
**Y** los textos deben fusionarse o mostrarse de forma coherente sin duplicados

### CA-7: Actualización dinámica de configuración
**Dado** que la configuración de códigos RAT en el CCP cambia para un procedimiento  
**Cuando** un ciudadano inicia una nueva tramitación después del cambio  
**Entonces** el sistema debe aplicar la nueva configuración  
**Y** debe mostrar u ocultar el bloque LOPD según la configuración actualizada

### CA-8: Consistencia entre pantallas
**Dado** que el sistema evalúa la presencia de códigos RAT  
**Cuando** determina mostrar u ocultar el bloque LOPD  
**Entonces** la decisión debe ser consistente en Paso Inicial, Resumen y PDF/HTML  
**Y** no debe existir discrepancia entre las diferentes ubicaciones para el mismo procedimiento

---

*Historia creada: 19/02/2026*

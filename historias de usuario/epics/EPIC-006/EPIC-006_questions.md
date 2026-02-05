# EPIC-003: Preguntas Abiertas y Supuestos

## Preguntas Abiertas (Priorizadas)

### Alta Prioridad - Bloqueantes

#### P1: Tipos de autorización soportados
**Pregunta:** ¿Cuántos tipos de autorizaciones existen en el sistema? ¿Solo "salvo oposición" y "únicamente si consiente", o hay más?

**Contexto:** Para implementar correctamente todas las variantes de autorizaciones

**Impacto:** Bloqueante para completar la funcionalidad

**Responsable de responder:** Equipo funcional / Analistas

**Respuesta**: sólo existen esos dos tipos de Autorización
---

#### P2: Configuración de autorizaciones por procedimiento
**Pregunta:** ¿Cómo se configuran las autorizaciones para cada procedimiento? ¿Existe una lista predefinida o se configuran manualmente?

**Contexto:** Necesario para entender de dónde provienen las autorizaciones a mostrar

**Impacto:** Bloqueante para la implementación

**Responsable de responder:** Gestores de procedimientos

**Respuesta**: Las autorizaciones vienen configuradas en el CCP donde se indica además, si son por Ley, bajo consentimiento o bajo autorización expresa
---

#### P3: Justificación de oposición
**Pregunta:** ¿Es obligatorio justificar el motivo de oposición a la consulta de datos? La imagen muestra "justificar el motivo a continuación" pero no se ve un campo de texto.

**Contexto:** Para implementar US-017 correctamente

**Impacto:** Alto - afecta a la funcionalidad de oposición

**Responsable de responder:** Equipo funcional / Legal

**Respuesta**: 
---

#### P4: Relación entre autorizaciones y documentos
**Pregunta:** ¿Cómo se determina qué documentos son obligatorios cuando el ciudadano se opone o no autoriza? ¿Existe una relación directa configurada?

**Contexto:** Para implementar US-020 correctamente

**Impacto:** Bloqueante para la lógica de documentos obligatorios

**Responsable de responder:** Equipo funcional / Analistas

**Respuesta**: Las autorizaciones en realidad son documentos. si se autoriza su consulta no es necesario aportarlos en el paso 4-Documentos. En caso de que se oponga o no se autorice su consulta, aparecerán como documentos a adjuntar en el paso 4

---

### Prioridad Media - Funcionales

#### P5: Oposición selectiva
**Pregunta:** ¿El ciudadano puede oponerse a la consulta de algunos datos pero no de otros, o la oposición es global a todos los datos de la sección?

**Contexto:** Las imágenes muestran un único toggle, sugiriendo oposición global

**Impacto:** Medio - afecta al diseño de la interfaz

**Responsable de responder:** Equipo funcional / UX

**Respuesta**: Es una oposición global. O se opone a la consulta de todos o a ninguno.

---

#### P6: Autorizaciones "por Ley"
**Pregunta:** ¿Existen autorizaciones que se consultan "por Ley" sin posibilidad de oposición? ¿Cómo se muestran al ciudadano?

**Contexto:** Para completar todos los tipos de autorizaciones

**Impacto:** Medio - funcionalidad adicional

**Responsable de responder:** Equipo funcional / Legal

**Respuesta**: 

---

#### P7: Modificación de autorizaciones
**Pregunta:** ¿El ciudadano puede cambiar sus decisiones de autorización después de avanzar al siguiente paso? ¿O quedan bloqueadas?

**Contexto:** Navegación y edición de pasos anteriores

**Impacto:** Medio - afecta a la experiencia de usuario

**Responsable de responder:** Product Owner / UX

**Respuesta**: Mientras no presente la solicitud, puede avanzar y retroceder a este pao para poder cambiar lo que considere

---

#### P8: Recuperación de borradores
**Pregunta:** ¿Se conservan las decisiones de autorización cuando el ciudadano guarda un borrador y lo recupera más tarde?

**Contexto:** Funcionalidad de borradores

**Impacto:** Medio - experiencia de usuario

**Responsable de responder:** Equipo funcional

**Respuesta**: Si, el borrador guarda toda la información rellenada por el solicitante. Es un comportamiento intrínseco de la funcionalidad de "borradores"
---

#### P9: Autorizaciones en representación
**Pregunta:** Cuando se tramita "Para otro" o como profesional, ¿las autorizaciones se refieren a los datos del interesado o del tramitador?

**Contexto:** Integración con EPIC-002 (Procedimientos profesionales)

**Impacto:** Medio - claridad en representación

**Responsable de responder:** Equipo funcional

**Respuesta**: siempre se refieren al interesado a efectos de la Ley. En el caso de representaciones, a la persona representada.

---

### Prioridad Baja - Mejoras futuras

#### P10: Historial de consultas autorizadas
**Pregunta:** ¿Se debe mostrar al ciudadano un historial de las consultas de datos que ha autorizado en solicitudes anteriores?

**Contexto:** Transparencia y trazabilidad

**Impacto:** Bajo - funcionalidad futura

**Responsable de responder:** Product Owner

**Respuesta**: No procede

---

## Supuestos (Asumidos hasta que se confirme lo contrario)

### SUPUESTO 1: Dos tipos principales de autorización
**Descripción:** Asumimos que existen dos tipos principales de autorizaciones:
- "Salvo oposición": Se autoriza por defecto, el ciudadano puede oponerse
- "Únicamente si consiente": Requiere autorización explícita del ciudadano

**Riesgo si es incorrecto:** Medio - Requeriría implementar tipos adicionales

---

### SUPUESTO 2: Oposición global
**Descripción:** Asumimos que la oposición a "Consulta de datos de la Administración" es global (todos los datos de esa sección), no selectiva por dato.

**Justificación:** La interfaz muestra un único toggle "Me opongo a la consulta de los datos"

**Riesgo si es incorrecto:** Medio - Cambio en diseño de interfaz

---

### SUPUESTO 3: Justificación opcional
**Descripción:** Asumimos que justificar el motivo de oposición es opcional, aunque se sugiere.

**Riesgo si es incorrecto:** Bajo - Añadir campo obligatorio

---

### SUPUESTO 4: Sin autorizaciones = sin paso
**Descripción:** Asumimos que si un procedimiento no tiene autorizaciones configuradas, el paso 3 no se muestra en el stepper.

**Riesgo si es incorrecto:** Bajo - Mostrar paso vacío

---

### SUPUESTO 5: Relación autorización-documento configurada
**Descripción:** Asumimos que existe una configuración que relaciona cada autorización con los documentos que deben aportarse si no se autoriza.

**Riesgo si es incorrecto:** Alto - Requeriría definir esta relación

---

### SUPUESTO 6: Decisiones modificables
**Descripción:** Asumimos que el ciudadano puede modificar sus decisiones de autorización mientras no haya enviado la solicitud, navegando de vuelta al paso 3.

**Riesgo si es incorrecto:** Bajo - Cambio en lógica de navegación

---

### SUPUESTO 7: Autorizaciones por procedimiento
**Descripción:** Asumimos que las autorizaciones se configuran a nivel de procedimiento-acción telemática, no son globales.

**Riesgo si es incorrecto:** Bajo - Cambio en configuración

---

### SUPUESTO 8: Organismo cedente obligatorio
**Descripción:** Asumimos que todo dato a consultar debe tener asociado un organismo cedente configurado.

**Riesgo si es incorrecto:** Bajo - Manejo de casos sin cedente

---

### SUPUESTO 9: Registro de decisiones
**Descripción:** Asumimos que todas las decisiones de autorización se registran junto con la solicitud para trazabilidad y para determinar qué datos se consultarán.

**Riesgo si es incorrecto:** Bajo - Es lógica de negocio estándar

---

### SUPUESTO 10: Autorizaciones en borradores
**Descripción:** Asumimos que las decisiones de autorización se guardan en los borradores y se recuperan al reanudar.

**Riesgo si es incorrecto:** Medio - Experiencia de usuario afectada

---

## Decisiones Pendientes

### DP1: Formato de cedente
**Decisión requerida:** ¿Se debe mostrar solo la palabra "Cedente" o el nombre completo del organismo cedente?

**Propuesta:** Mostrar el nombre del organismo para mayor claridad

**Responsable:** UX / Equipo funcional

**Fecha límite:** Antes de implementar US-019

---

### DP2: Texto del mensaje de oposición
**Decisión requerida:** Validar los textos exactos de los mensajes informativos cuando el ciudadano se opone o no autoriza.

**Responsable:** Equipo de contenidos / Legal

**Fecha límite:** Antes de implementar US-017 y US-018

---

### DP3: Campo de justificación
**Decisión requerida:** ¿Se debe incluir un campo de texto para que el ciudadano justifique su oposición? ¿Es obligatorio?

**Propuesta:** Campo opcional de texto libre

**Responsable:** Equipo funcional / Legal

**Fecha límite:** Antes de implementar US-017

---

### DP4: Orden de secciones
**Decisión requerida:** ¿Se debe mostrar primero "Consulta de datos de la Administración" y luego "Consulta de datos tributarios", o puede variar?

**Propuesta:** Orden configurable por procedimiento

**Responsable:** Equipo funcional

**Fecha límite:** Durante diseño de configuración

---

## Riesgos Identificados

| ID | Riesgo | Probabilidad | Impacto | Mitigación |
|----|--------|--------------|---------|------------|
| R1 | Falta de claridad en tipos de autorización | Media | Alto | Validar con equipo funcional y legal todos los tipos |
| R2 | Relación autorización-documento no definida | Media | Alto | Definir modelo de configuración tempranamente |
| R3 | Ciudadano confundido sobre consecuencias de no autorizar | Media | Medio | Textos claros validados con UX y pruebas de usabilidad |
| R4 | Justificación obligatoria no implementada | Baja | Medio | Clarificar requisito legal |
| R5 | Incompatibilidad con procedimientos sin autorizaciones | Baja | Bajo | Validar que el paso se oculta correctamente |

---

**Última actualización:** 27/01/2026  
**Responsable:** Product Owner Assistant  
**Próxima revisión:** Al completar las respuestas a preguntas prioritarias

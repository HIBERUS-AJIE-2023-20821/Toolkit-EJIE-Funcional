# EPIC-006: Preguntas Abiertas y Supuestos

---
**Actualización importante**: El diseño de la pantalla ha cambiado. Ahora incluye una pregunta global inicial con radiobutton (Sí/No) y dos bloques con switches generales y checkboxes individuales por dato.
---

## Preguntas Abiertas (Priorizadas)

### Alta Prioridad - Bloqueantes

#### P1: Tipos de autorización soportados ✅ RESPONDIDA
**Pregunta:** ¿Cuántos tipos de autorizaciones existen en el sistema? ¿Solo "salvo oposición" y "únicamente si consiente", o hay más?

**Contexto:** Para implementar correctamente todas las variantes de autorizaciones

**Impacto:** Bloqueante para completar la funcionalidad

**Responsable de responder:** Equipo funcional / Analistas

**Respuesta**: Existen tres tipos en el CCP: "por Ley", "salvo oposición" y "únicamente si consiente". Solo los dos últimos son modificables por el ciudadano y se muestran en pantalla. Los datos "por Ley" se incluyen automáticamente en la solicitud sin mostrarse en pantalla.
---

#### P2: Configuración de autorizaciones por procedimiento ✅ RESPONDIDA
**Pregunta:** ¿Cómo se configuran las autorizaciones para cada procedimiento? ¿Existe una lista predefinida o se configuran manualmente?

**Contexto:** Necesario para entender de dónde provienen las autorizaciones a mostrar

**Impacto:** Bloqueante para la implementación

**Responsable de responder:** Gestores de procedimientos

**Respuesta**: Las autorizaciones vienen configuradas en el CCP donde se indica además, si son por Ley, bajo consentimiento o bajo autorización expresa
---

#### P3: Justificación de oposición ✅ RESPONDIDA
**Pregunta:** ¿Es obligatorio justificar el motivo de oposición a la consulta de datos?

**Contexto:** Para implementar US-017 correctamente

**Impacto:** Alto - afecta a la funcionalidad de oposición

**Responsable de responder:** Equipo funcional / Legal

**Respuesta**: Sí, es OBLIGATORIO. Cuando el ciudadano marca oposición a cualquier dato (tipo "salvo oposición"), aparecerá un textarea donde debe especificar el motivo de su oposición. Este campo es obligatorio para poder continuar si hay alguna oposición marcada.
---

#### P4: Relación entre autorizaciones y documentos ✅ RESPONDIDA
**Pregunta:** ¿Cómo se determina qué documentos son obligatorios cuando el ciudadano se opone o no autoriza? ¿Existe una relación directa configurada?

**Contexto:** Para implementar US-020 correctamente

**Impacto:** Bloqueante para la lógica de documentos obligatorios

**Responsable de responder:** Equipo funcional / Analistas

**Respuesta**: Las autorizaciones en realidad son documentos. Si se autoriza su consulta no es necesario aportarlos en el paso 4-Documentos. En caso de que se oponga o no se autorice su consulta, aparecerán como documentos a adjuntar en el paso 4

---

#### P10: Estado indeterminado de controles
**Pregunta:** Cuando algunos checkboxes están marcados y otros no dentro de un mismo bloque, ¿el switch general debe mostrar un estado indeterminado (ej. línea horizontal) o simplemente estar desactivado?

**Contexto:** Para la sincronización de controles en US-020

**Impacto:** Alto - afecta al diseño de la interfaz

**Responsable de responder:** UX / Product Owner

**Respuesta**:  Aparecerá desactivado. Solo se activa si todos los checkboxes están marcados.

---

#### P11: Comportamiento al recuperar borrador
**Pregunta:** Al recuperar un borrador que tenía decisiones mixtas (algunos datos autorizados y otros no), ¿la pregunta global debe aparecer marcada en Sí, No, o sin seleccionar?

**Contexto:** Coherencia en recuperación de estado

**Impacto:** Medio - afecta a la experiencia de usuario

**Responsable de responder:** Product Owner / UX

**Respuesta**: Deberá aparecer según lo que corresponda en base a los switchs o checkboxes marcados y/o desmarcados

---

### Prioridad Media - Funcionales

#### P5: Oposición selectiva ✅ RESPONDIDA (CAMBIO DE DISEÑO)
**Pregunta:** ¿El ciudadano puede oponerse a la consulta de algunos datos pero no de otros, o la oposición es global a todos los datos de la sección?

**Contexto:** Las imágenes muestran un único toggle, sugiriendo oposición global

**Impacto:** Medio - afecta al diseño de la interfaz

**Responsable de responder:** Equipo funcional / UX

**Respuesta**: Con el nuevo diseño, la oposición es SELECTIVA. Existe un switch general pero cada dato tiene su propio checkbox que el ciudadano puede marcar/desmarcar individualmente.

---

#### P6: ~~Autorizaciones "por Ley"~~ ✅ RESPONDIDA
**Pregunta:** ¿Existen autorizaciones que se consultan "por Ley" sin posibilidad de oposición? ¿Cómo se muestran al ciudadano?

**Contexto:** Para completar todos los tipos de autorizaciones

**Impacto:** Medio - funcionalidad adicional

**Responsable de responder:** Equipo funcional / Legal

**Respuesta**: Existen en el CCP pero NO se muestran en esta pantalla ya que el ciudadano no tiene opción de intervención.

---

#### P7: Modificación de autorizaciones ✅ RESPONDIDA
**Pregunta:** ¿El ciudadano puede cambiar sus decisiones de autorización después de avanzar al siguiente paso? ¿O quedan bloqueadas?

**Contexto:** Navegación y edición de pasos anteriores

**Impacto:** Medio - afecta a la experiencia de usuario

**Responsable de responder:** Product Owner / UX

**Respuesta**: Mientras no presente la solicitud, puede avanzar y retroceder a este paso para poder cambiar lo que considere

---

#### P8: Recuperación de borradores ✅ RESPONDIDA
**Pregunta:** ¿Se conservan las decisiones de autorización cuando el ciudadano guarda un borrador y lo recupera más tarde?

**Contexto:** Funcionalidad de borradores

**Impacto:** Medio - experiencia de usuario

**Responsable de responder:** Equipo funcional

**Respuesta**: Sí, el borrador guarda toda la información rellenada por el solicitante. Es un comportamiento intrínseco de la funcionalidad de "borradores"
---

#### P9: Autorizaciones en representación ✅ RESPONDIDA
**Pregunta:** Cuando se tramita "Para otro" o como profesional, ¿las autorizaciones se refieren a los datos del interesado o del tramitador?

**Contexto:** Integración con EPIC-002 (Procedimientos profesionales)

**Impacto:** Medio - claridad en representación

**Responsable de responder:** Equipo funcional

**Respuesta**: Siempre se refieren al interesado a efectos de la Ley. En el caso de representaciones, a la persona representada.

---

#### P12: Texto de mensaje informativo
**Pregunta:** ¿El mensaje "Deberás aportar la documentación cuya consulta no autorices" debe mostrarse siempre visible o solo cuando hay alguna oposición/no autorización activa?

**Contexto:** Para implementar en US-017 y US-018

**Impacto:** Bajo - claridad de mensajes

**Responsable de responder:** UX / Product Owner

**Respuesta**: 

---

### Prioridad Baja - Mejoras futuras

#### P10: ~~Historial de consultas autorizadas~~ ✅ NO PROCEDE
**Pregunta:** ¿Se debe mostrar al ciudadano un historial de las consultas de datos que ha autorizado en solicitudes anteriores?

**Respuesta**: No procede

---

## Supuestos (Asumidos hasta que se confirme lo contrario)

### SUPUESTO 1: Tres tipos de autorizaciones, dos modificables ✅ CONFIRMADO
**Descripción:** Existen tres tipos de autorizaciones configuradas en el CCP:
- "Por Ley": La Administración puede consultar por mandato legal. **No se muestra en pantalla pero sí se incluye automáticamente en la solicitud**
- "Salvo oposición": Autorizada por defecto, el ciudadano puede oponerse selectivamente. **Se muestra en pantalla**
- "Únicamente si consiente": Requiere autorización explícita del ciudadano. **Se muestra en pantalla**

Solo los dos últimos tipos requieren interacción del ciudadano.

**Riesgo si es incorrecto:** N/A - Confirmado

---

### SUPUESTO 2: Oposición y autorización SELECTIVA ✅ CONFIRMADO (CAMBIO)
**Descripción:** Con el nuevo diseño, la oposición y autorización es SELECTIVA por cada dato individual, usando checkboxes. Existe un switch general que facilita marcar/desmarcar todos, pero el ciudadano puede ajustar individualmente.

**Justificación:** Diseño actualizado con pregunta global + switches generales + checkboxes individuales

**Riesgo si es incorrecto:** N/A - Confirmado por cambio de diseño

---

### SUPUESTO 3: Motivo de oposición obligatorio ✅ CONFIRMADO
**Descripción:** Cuando el ciudadano marca oposición a cualquier dato del bloque "salvo oposición", debe aparecer un textarea donde especificar el motivo. Este campo es obligatorio para poder continuar con la tramitación si hay alguna oposición activa.

**Justificación:** Requisito funcional confirmado para justificar la oposición del ciudadano

**Riesgo si es incorrecto:** N/A - Confirmado

---

### SUPUESTO 4: Sin autorizaciones modificables = sin paso ✅ VÁLIDO
**Descripción:** Si un procedimiento no tiene autorizaciones de tipo "salvo oposición" ni "únicamente si consiente" configuradas, el paso 3 no se muestra en el stepper. Las autorizaciones "por Ley" (si existen) se incluyen automáticamente en la solicitud sin afectar a la visualización del paso.

**Riesgo si es incorrecto:** Bajo - Mostrar paso vacío

---

### SUPUESTO 5: Relación autorización-documento configurada ✅ CONFIRMADO
**Descripción:** Existe una configuración que relaciona cada autorización con los documentos que deben aportarse si no se autoriza. Las autorizaciones son en realidad documentos en el CCP.

**Riesgo si es incorrecto:** N/A - Confirmado

---

### SUPUESTO 6: Decisiones modificables ✅ CONFIRMADO
**Descripción:** El ciudadano puede modificar sus decisiones de autorización mientras no haya enviado la solicitud, navegando de vuelta al paso 3.

**Riesgo si es incorrecto:** N/A - Confirmado

---

### SUPUESTO 7: Autorizaciones por procedimiento ✅ CONFIRMADO
**Descripción:** Las autorizaciones se configuran a nivel de procedimiento-acción telemática en el CCP, no son globales.

**Riesgo si es incorrecto:** N/A - Confirmado

---

### SUPUESTO 8: Organismo cedente obligatorio ✅ VÁLIDO
**Descripción:** Todo dato a consultar debe tener asociado un organismo cedente configurado que se muestra junto a cada checkbox.

**Riesgo si es incorrecto:** Bajo - Manejo de casos sin cedente

---

### SUPUESTO 9: Registro de decisiones ✅ CONFIRMADO
**Descripción:** Todas las decisiones de autorización se registran junto con la solicitud para trazabilidad y para determinar qué datos se consultarán y qué documentos son obligatorios.

**Riesgo si es incorrecto:** N/A - Confirmado

---

### SUPUESTO 10: Pregunta global obligatoria
**Descripción:** La pregunta global "¿Autorizas a la Administración a consultar tus datos?" es obligatoria de responder para habilitar los bloques y poder continuar al siguiente paso.

**Justificación:** Diseño de pantalla con pregunta global como primer elemento

**Riesgo si es incorrecto:** Medio - Cambio en lógica de validación

---

### SUPUESTO 11: Sincronización bidireccional
**Descripción:** La sincronización entre pregunta global, switches y checkboxes es bidireccional y automática:
- Cambios en pregunta global → afectan switches y checkboxes
- Cambios en checkboxes → pueden afectar switches y pregunta global

**Justificación:** Necesario para coherencia y experiencia de usuario

**Riesgo si es incorrecto:** Alto - Cambio importante en comportamiento de controles

---

### SUPUESTO 12: Sin validación de autorizaciones individuales
**Descripción:** No existe validación obligatoria sobre autorizaciones específicas. El ciudadano puede no autorizar ningún dato si lo desea (tendrá que aportar todos los documentos). Solo es obligatorio responder la pregunta global.

**Justificación:** Libertad del ciudadano para decidir

**Riesgo si es incorrecto:** Medio - Añadir validaciones específicas

---

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

# EPIC-002: Preguntas Abiertas y Supuestos

## Preguntas Abiertas (Priorizadas)

### Alta Prioridad - Bloqueantes

#### P1: Configuración del indicador "profesional" en procedimientos
**Pregunta:** ¿Cómo se identifica en el CCP (Catálogo de Configuración de Procedimientos) si un procedimiento está marcado como profesional?

**Contexto:** Necesario para implementar US-008 (identificación de procedimiento profesional)

**Impacto:** Bloqueante para el desarrollo

**Responsable de responder:** Equipo funcional / Gestor de procedimientos

---

#### P2: Estructura de datos para registro del profesional
**Pregunta:** ¿Qué información específica del profesional tramitador debe registrarse en el sistema al enviar una solicitud? ¿Existe ya un formato definido?

**Información requerida:**
- Datos del profesional a registrar
- Cómo se distingue del interesado
- Dónde se almacena esta información

**Contexto:** Necesario para implementar US-015 (registro de datos del profesional)

**Impacto:** Bloqueante para la integración del registro

**Responsable de responder:** Equipo funcional / Analistas de sistemas

---

#### P3: Consulta de empresas autorizadoras
**Pregunta:** ¿Cómo se obtiene la lista de empresas que han autorizado a un profesional? ¿Existe un servicio disponible para consultarlas?

**Contexto:** Necesario para implementar US-013 (tramitación como autorizado de empresa)

**Impacto:** Bloqueante para la modalidad de autorizado de empresa

**Responsable de responder:** Equipo funcional / Gestores de registro de apoderamientos

---

#### P4: Tipología del documento acreditativo
**Pregunta:** ¿Cuál es la tipología exacta del documento acreditativo de representación que debe aportarse en tramitaciones "Para otro"?

**Contexto:** Necesario para configurar correctamente el documento obligatorio en US-012

**Responsable de responder:** Equipo funcional / Gestores documentales

---

### Prioridad Media - Funcionales

#### P5: Notificaciones al interesado representado
**Pregunta:** ¿Se debe permitir opcionalmente que el profesional configure el envío de copia de notificaciones al interesado representado (en tramitación "Para otro" y "Como autorizado")?

**Contexto:** Por defecto, las notificaciones van solo al profesional (US-014)

**Impacto:** Funcionalidad adicional que mejoraría la experiencia

**Responsable de responder:** Product Owner / Equipo funcional

---

#### P6: Validación de autorizaciones profesionales
**Pregunta:** ¿Existe algún mecanismo de validación de que el usuario autenticado es realmente un profesional autorizado (colegio profesional, registro oficial)? ¿O cualquier ciudadano puede elegir el perfil "profesional"?

**Contexto:** Seguridad y validación de perfiles profesionales

**Impacto:** Puede requerir validaciones adicionales

**Responsable de responder:** Equipo de seguridad / Equipo funcional

---

#### P7: Caducidad de autorizaciones
**Pregunta:** ¿Cómo se gestiona la caducidad de autorizaciones de empresa durante una tramitación en curso? ¿Qué sucede si la autorización caduca entre el inicio y el envío de la solicitud?

**Contexto:** Validación de vigencia de autorizaciones

**Impacto:** Manejo de errores y validaciones

**Responsable de responder:** Equipo funcional / Gestores de registro de apoderamientos

---

#### P8: Visibilidad de borradores
**Pregunta:** ¿Cómo funciona la visibilidad de borradores cuando la autorización está asociada a un centro específico de la empresa? ¿Solo el profesional que creó el borrador lo ve, o todos los profesionales autorizados del mismo centro?

**Contexto:** Compartición de borradores en tramitación "Como autorizado"

**Impacto:** Funcionalidad de gestión de borradores

**Responsable de responder:** Equipo funcional

---

#### P9: Multiinteresado con profesional
**Pregunta:** En solicitudes multiinteresado tramitadas por profesional, ¿el profesional debe ser el mismo para todos los interesados o pueden tener profesionales diferentes?

**Contexto:** Diseño de multiinteresado profesional

**Impacto:** Complejidad del flujo de tramitación

**Responsable de responder:** Equipo funcional

---

#### P10: Cambio de email post-envío
**Pregunta:** ¿Se debe permitir que el profesional cambie el email de notificaciones después de haber enviado la solicitud?

**Contexto:** Gestión de notificaciones (US-014)

**Impacto:** Funcionalidad adicional de gestión

**Responsable de responder:** Product Owner / Equipo funcional

---

### Prioridad Baja - Mejoras futuras

#### P11: Estadísticas de procedimientos profesionales
**Pregunta:** ¿Se requiere algún tipo de reporting o estadísticas específicas para procedimientos profesionales (número de solicitudes por profesional, tipos más frecuentes, etc.)?

**Contexto:** Análisis y métricas

**Impacto:** Funcionalidad futura no crítica

**Responsable de responder:** Product Owner

---

## Supuestos (Asumidos hasta que se confirme lo contrario)

### SUPUESTO 1: Indicador de procedimiento profesional
**Descripción:** Asumimos que existe un campo en el CCP (Catálogo de Configuración de Procedimientos) que permite marcar si un procedimiento está orientado a profesionales.

**Riesgo si es incorrecto:** Alto - Requeriría definir cómo identificar procedimientos profesionales

**Plan de mitigación:** Validar con gestores de procedimientos en la primera iteración

---

### SUPUESTO 2: Sin validación de perfil profesional
**Descripción:** Asumimos que NO existe validación externa de que el usuario es realmente un profesional autorizado. Cualquier ciudadano autenticado puede elegir tramitar como "profesional".

**Justificación:** El documento indica: "también puede rellenarlo y enviarlo cualquier persona ciudadana"

**Riesgo si es incorrecto:** Medio - Requeriría integración con sistema de validación de profesionales

---

### SUPUESTO 3: No se envían copias al interesado representado
**Descripción:** Asumimos que en tramitaciones "Para otro" y "Como autorizado", las notificaciones se envían ÚNICAMENTE al profesional, sin copia automática al interesado.

**Justificación:** El documento indica: "Las notificaciones se enviarán siempre al profesional"

**Riesgo si es incorrecto:** Bajo - Es modificación de configuración de notificaciones

---

### SUPUESTO 4: Documento acreditativo solo para "Para otro"
**Descripción:** Asumimos que el documento acreditativo de representación es obligatorio SOLO en tramitación "Para otro", NO en "Como autorizado de empresa" (porque la autorización ya existe en el registro correspondiente).

**Justificación:** Lógica de negocio - La autorización empresarial ya está registrada

**Riesgo si es incorrecto:** Medio - Cambio en flujo de documentos

---

### SUPUESTO 5: Un solo profesional por solicitud
**Descripción:** Asumimos que una solicitud solo puede ser tramitada por UN profesional. No se permite tramitación colaborativa entre múltiples profesionales.

**Riesgo si es incorrecto:** Medio - Requeriría rediseño de la funcionalidad

---

### SUPUESTO 6: Email obligatorio para profesionales
**Descripción:** Asumimos que el email es un campo obligatorio para usuarios que desean tramitar como profesionales. Sin email, no se permite continuar.

**Justificación:** Es necesario para el sistema de notificaciones

**Riesgo si es incorrecto:** Bajo - Gestión de casos sin email

---

### SUPUESTO 7: Procedimiento puede ser tramitado como ciudadano o profesional
**Descripción:** Asumimos que cuando un procedimiento está marcado como "profesional", se muestra la información pero el usuario puede elegir continuar como ciudadano. No es exclusivo para profesionales.

**Justificación:** El documento indica: "también puede rellenarlo y enviarlo cualquier persona ciudadana"

**Riesgo si es incorrecto:** Bajo - Cambio de lógica de presentación

---

### SUPUESTO 8: Autorizaciones vigentes
**Descripción:** Asumimos que la consulta de empresas autorizadoras devuelve únicamente autorizaciones vigentes (no caducadas ni revocadas).

**Riesgo si es incorrecto:** Medio - Requeriría validación adicional de vigencia

**Plan de mitigación:** Implementar validación de fecha de vigencia

---

### SUPUESTO 9: Borradores mantienen modalidad
**Descripción:** Asumimos que cuando un profesional guarda un borrador, la modalidad de tramitación seleccionada (Para mí, Para otro, Como autorizado) se conserva al recuperar el borrador.

**Riesgo si es incorrecto:** Bajo - Pérdida de contexto en recuperación de borradores

---

### SUPUESTO 10: Profesional puede tramitar multiinteresado
**Descripción:** Asumimos que si el procedimiento permite multiinteresado, el profesional puede añadir varios interesados y actuar como tramitador de todos ellos.

**Riesgo si es incorrecto:** Medio - Limitación funcional

---

## Decisiones Pendientes

### DP1: Textos informativos
**Decisión requerida:** Validar con equipo funcional los textos exactos de la ventana informativa de procedimiento profesional.

**Propuesta actual:** "Dada su naturaleza técnica, este procedimiento está orientado a Profesionales. No obstante, también puede rellenarlo y enviarlo cualquier persona ciudadana."

**Responsable:** Equipo funcional / Contenidos

**Fecha límite:** Antes de implementar US-009

---

### DP2: Orden de implementación
**Decisión requerida:** ¿Se deben implementar las tres modalidades de tramitación (Para mí, Para otro, Como autorizado) simultáneamente o en fases?

**Propuesta:** 
- Fase 1: "Para mí" (US-011) - Más simple
- Fase 2: "Para otro" (US-012) - Complejidad media
- Fase 3: "Como autorizado" (US-013) - Más complejo

**Responsable:** Product Owner / Equipo de desarrollo

**Fecha límite:** Sprint Planning

---

### DP3: Manejo de errores en consulta de empresas
**Decisión requerida:** ¿Qué comportamiento debe tener el sistema si la consulta de empresas autorizadoras falla: bloquear toda tramitación profesional, permitir continuar sin autorizaciones, o mostrar error solo en "Como autorizado"?

**Propuesta:** Mostrar error solo en opción "Como autorizado", permitiendo usar "Para mí" o "Para otro"

**Responsable:** Product Owner / Equipo funcional

**Fecha límite:** Antes de implementar US-013

---

### DP4: Internacionalización
**Decisión requerida:** Confirmar si los textos deben estar disponibles en euskera, castellano e inglés.

**Responsable:** Product Owner

**Fecha límite:** Antes de implementar US-009 y US-010

---

## Riesgos Identificados

| ID | Riesgo | Probabilidad | Impacto | Mitigación |
|----|--------|--------------|---------|------------|
| R1 | El sistema no tiene configurado el indicador de procedimiento profesional | Media | Alto | Coordinar con gestores para añadirlo si no existe |
| R2 | No existe forma de registrar datos del profesional tramitador | Media | Alto | Validación temprana del modelo de datos |
| R3 | Servicio de empresas autorizadoras no disponible | Media | Alto | Implementar mock para desarrollo, coordinar disponibilidad |
| R4 | Usuarios confundidos por la información profesional | Media | Medio | Pruebas de usabilidad, textos claros |
| R5 | Notificaciones no llegan al profesional por problemas de email | Media | Alto | Validación estricta de email, logs de auditoría |

---

**Última actualización:** 27/01/2026  
**Responsable:** Product Owner Assistant  
**Próxima revisión:** Al completar las respuestas a preguntas prioritarias

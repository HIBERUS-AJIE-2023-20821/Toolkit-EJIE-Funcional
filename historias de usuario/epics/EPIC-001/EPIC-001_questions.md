# Preguntas abiertas y supuestos - EPIC-001: Subsanación

---

## PREGUNTAS ABIERTAS

### Prioridad Alta (bloquean desarrollo o decisiones críticas)

**P-001**: ¿Existe notificación automática al ciudadano tras el envío exitoso de la subsanación además del justificante descargable?
- **Impacto**: Requiere integración con sistema corporativo de notificaciones/email
- **Afecta a**: US-007 (confirmación de envío)
- **Decisión necesaria de**: Product Owner, Arquitecto de integración

**P-002**: ¿Qué sucede si falla el almacenamiento en Dokusi pero el envío a PPS es exitoso, o viceversa? ¿Hay transaccionalidad distribuida?
- **Impacto**: Define estrategia de recuperación ante errores y consistencia de datos
- **Afecta a**: US-007 (generación PDF y envío)
- **Decisión necesaria de**: Arquitecto técnico, Product Owner

**P-003**: ¿Cómo se notifica al funcionario tramitador de que hay una subsanación recibida? ¿Es responsabilidad de PPS o del Orquestador?
- **Impacto**: Define alcance de funcionalidad de notificaciones
- **Afecta a**: US-007 (tras envío exitoso)
- **Decisión necesaria de**: Product Owner, responsable de PPS

### Prioridad Media (afectan funcionalidad pero no bloquean MVP)

**P-004**: ¿Puede un ciudadano tener múltiples requerimientos de subsanación pendientes para el mismo expediente simultáneamente?
- **Impacto**: Define si se gestionan múltiples requerimientos en paralelo o secuencialmente
- **Afecta a**: US-001 (acceso al proceso), modelo de datos
- **Decisión necesaria de**: Product Owner, Analista funcional

**P-005**: ¿Existe límite global en la cantidad total de documentos que se pueden adjuntar en una subsanación?
- **Impacto**: Define validaciones y mensajes de error, capacidad de Dokusi
- **Afecta a**: US-004 (gestión de documentos)
- **Decisión necesaria de**: Product Owner, responsable de Dokusi

**P-006**: ¿Se permite guardar múltiples borradores de la misma subsanación o solo el más reciente? (Contexto indica "solo el más reciente" según RB-31)
- **Impacto**: Simplificación confirmada según contexto actual
- **Afecta a**: US-003 (guardado de borrador)
- **Decisión**: CONFIRMADO - Solo borrador más reciente según RB-31

**P-007**: ¿El guardado de borradores es solo manual o también hay guardado automático periódico?
- **Impacto**: Define UX y riesgo de pérdida de datos
- **Afecta a**: US-003 (edición de campos)
- **Decisión necesaria de**: Product Owner, UX Designer

### Prioridad Baja (mejoras o casos edge)

**P-008**: ¿Se requiere soporte multiidioma obligatorio (euskera, castellano) o es opcional inglés/francés?
- **Impacto**: Volumen de traducciones y testing
- **Afecta a**: Todas las US
- **Decisión necesaria de**: Product Owner, Legal/Cumplimiento
- **Nota del contexto**: Euskera y castellano son OBLIGATORIOS. Inglés y francés opcionales.

**P-009**: ¿Existe un tiempo máximo de sesión antes de cerrar automáticamente el proceso?
- **Impacto**: Define comportamiento de timeout y recuperación de sesión
- **Afecta a**: US-001, US-003 (gestión de sesión)
- **Decisión necesaria de**: Arquitecto técnico, Seguridad
- **Nota**: Gestionado por infraestructura según SUPUESTO-21 del contexto

**P-010**: ¿Los representantes con RdA pueden delegar en otros sub-representantes dentro del proceso de subsanación?
- **Impacto**: Complejidad adicional de gestión de permisos
- **Afecta a**: US-002 (participantes)
- **Decisión necesaria de**: Product Owner, responsable de RdA

---

## DECISIONES PENDIENTES

**D-001**: **Plantilla corporativa del PDF justificante**
- ¿Existe plantilla corporativa específica o normativa de formato?
- Responsable decisión: Comunicación corporativa, Legal

**D-002**: **Estrategia de reintentos ante fallos**
- Número de reintentos: ¿3 reintentos es adecuado? ¿Espera incremental (1s, 2s, 4s)?
- Cola de reintento diferido: ¿Cada 15 minutos? ¿Ventana máxima de reintentos?
- Responsable decisión: Arquitecto técnico

**D-003**: **Nivel de detalle en logs de auditoría**
- ¿Qué campos específicos se registran en cada evento?
- ¿Se registran datos sensibles (valores de campos) o solo metadatos?
- Responsable decisión: Seguridad, DPO (Data Protection Officer), Auditoría

**D-004**: **Disponibilidad de entornos de integración**
- ¿Están disponibles entornos de pruebas para Dokusi, PPS, CCP, RdA?
- ¿Existen datos de prueba/mock para testing integral?
- Responsable decisión: Arquitecto de integración, responsables de sistemas corporativos

**D-005**: **Accesibilidad WCAG 2.1 nivel AA**
- ¿Es obligatorio cumplimiento WCAG 2.1 nivel AA? (contexto indica que SÍ - ver NFR)
- ¿Se requiere certificación formal por entidad acreditada?
- Responsable decisión: Legal, Accesibilidad corporativa
- **Nota**: Contexto confirma WCAG 2.1 nivel AA OBLIGATORIO

---

## SUPUESTOS (Pendientes de validación)

### Supuestos sobre sistemas externos

**SUPUESTO-01**: El sistema que notifica al ciudadano del requerimiento de subsanación proporciona enlace con parámetros correctos (Folder ID, Instance ID, ID acción telemática)

**SUPUESTO-02**: CCP proporciona configuraciones correctas y completas de procedimientos y acciones telemáticas tipo "Subsanación"

**SUPUESTO-03**: El funcionario tramitador ha marcado correctamente los campos y documentos a subsanar en el cliente de tramitación/backoffice

**SUPUESTO-04**: Dokusi tiene capacidad suficiente para almacenar todos los documentos generados durante subsanaciones

**SUPUESTO-05**: PPS está disponible para recibir subsanaciones en tiempo real y proporciona número de registro único

**SUPUESTO-06**: RdA mantiene datos actualizados y en tiempo real de apoderamientos y autorizaciones vigentes

**SUPUESTO-07**: EraiKIT tiene formularios específicos configurados para subsanaciones (pueden ser diferentes a formularios de solicitud inicial)

### Supuestos sobre comportamiento de usuario

**SUPUESTO-08**: Los ciudadanos disponen de navegadores web actualizados compatibles con el sistema (Chrome, Firefox, Safari, Edge versiones recientes)

**SUPUESTO-09**: Los ciudadanos tienen acceso a medios digitales para generar/escanear los documentos requeridos (escáner, cámara smartphone, etc.)

**SUPUESTO-10**: Los emails de los ciudadanos registrados son válidos y accesibles para recibir justificantes

### Supuestos sobre la funcionalidad

**SUPUESTO-11**: NO se requiere firma electrónica para subsanaciones, solo autenticación del ciudadano (a diferencia de solicitudes iniciales)

**SUPUESTO-12**: El guardado de borradores es MANUAL por el ciudadano (no automático periódico) - Decisión de diseño para subsanaciones

**SUPUESTO-13**: Solo se mantiene un borrador activo por requerimiento de subsanación (el más reciente según RB-31)

**SUPUESTO-14**: El tamaño máximo por documento es de 10MB según estándar corporativo (configurable en CCP según RB-38)

**SUPUESTO-15**: Los formatos de documento permitidos (PDF, DOC, DOCX, JPG, PNG) son configurables por tipo de documento en CCP

**SUPUESTO-16**: NO se permite prerrellenado automático mediante SVTs en subsanaciones (los campos vienen con valores previos a corregir)

**SUPUESTO-17**: Los requerimientos de subsanación tienen fecha límite de respuesta, gestionada fuera del Orquestador

### Supuestos técnicos

**SUPUESTO-18**: Los servicios corporativos (Dokusi, PPS, CCP, RdA) tienen SLAs adecuados con tiempo de respuesta < 2 segundos en el 95% de casos

**SUPUESTO-19**: La generación de PDF justificante con código QR debe completarse en menos de 15 segundos según NFR

**SUPUESTO-20**: Los mecanismos de defensa ante bots y ataques están implementados a nivel de infraestructura/gateway

**SUPUESTO-21**: El tiempo de sesión antes de timeout automático es gestionado por infraestructura (no por Orquestador) y es suficiente para completar subsanaciones

**SUPUESTO-22**: Las pruebas de estrés con herramientas EJIE son obligatorias antes de paso a producción según contexto

**SUPUESTO-23**: El número de registro generado por PPS sigue formato "SUBS-YYYY-NNNNN" o similar y es único e irrepetible (RB-48, RB-49)

---

## CONFIRMACIONES DEL CONTEXTO

Estos puntos están CONFIRMADOS según el context.md actualizado:

✅ **Multiidioma**: Euskera y castellano OBLIGATORIOS. Inglés y francés opcionales.

✅ **Accesibilidad**: WCAG 2.1 nivel AA OBLIGATORIO según NFR.

✅ **Solo borrador más reciente**: Confirmado por RB-31 (solo se mantiene el borrador más reciente).

✅ **NO requiere firma electrónica**: Las subsanaciones NO requieren firma (a diferencia de solicitudes iniciales con firma simple/múltiple).

✅ **Inmutabilidad**: Una vez enviada la subsanación, NO se puede modificar (RB-33).

✅ **Representación**: RdA proporciona apoderamientos, pero NO se puede usar "Para otro" en subsanaciones (los interesados ya están definidos en el expediente).

✅ **Código QR**: Dokusi genera código QR para cada documento almacenado (RB-39).

✅ **Tamaño máximo documentos**: Configurable en CCP, típicamente 10MB (RB-38).

✅ **Auditoría inmutable**: Todos los registros de auditoría son inmutables (RB-44, RB-45).

---

*Documento creado: 26/01/2026*  
*Última actualización: 26/01/2026*  
*Estado: Pendiente de validación con Product Owner y stakeholders*

# EPIC-002: Preguntas y Supuestos

## Preguntas abiertas (priorizadas)

### Prioridad Alta

1. **Almacenamiento de campos marcados**: ¿En qué tabla/entidad de la base de datos se almacenarán los campos marcados para subsanación y sus motivos? ¿Existe ya un modelo de datos definido?
**Respuesta**: No aplica. Se definirá en tareas técnicas más adelante

2. **Formato de almacenamiento del motivo**: ¿El motivo del campo marcado se almacena como texto libre sin límite o tiene un tamaño máximo definido (ej: 500 caracteres)?
**Respuesta**: No aplica. Es responsabilidad de la aplicación de tramitación.

3. **Identificación de campos**: ¿Cómo se identifican unívocamente los campos del formulario en la base de datos? ¿Por ID técnico, por path/ruta del campo, por código CCP?
**Respuesta**: No aplica. Se almacenará el identificador del componente.

4. **Integración con sistema de tramitación**: ¿Desde qué sistema específico accede el tramitador al expediente? ¿PPS? ¿Otro sistema de tramitación? ¿Cómo se integra con el marcaje de campos?
**Respuesta**: Desde el Cliente de Tramitación/Tramitagune

5. **Acceso a los campos marcados**: ¿Qué otros sistemas necesitan consumir la información de campos marcados? ¿Solo el Orquestador para presentar al ciudadano o también otros aplicativos?
**Respuesta**: Sólo el Orquestador.

### Prioridad Media

6. **Edición de campos marcados**: Una vez guardados los campos marcados, ¿puede el tramitador modificarlos o eliminarlos antes de que se procese el requerimiento? ¿Hay un estado "borrador" vs "definitivo"?
**Respuesta**: El tramitador podrá acceder a marcar nuevos campos o desmarcar los marcados previamente mientras no se finalice el proceso completo que finaliza con el envío de la notificación. Responsabilidad del cliente de tramitación dar o no acceso a la pantalla de marcar campos

7. **Campos obligatorios vs opcionales**: ¿Es necesario que el tramitador indique si un campo marcado es de subsanación obligatoria u opcional, o todos se consideran obligatorios por defecto?
**Respuesta**: No. La obligatoriedad de los campos viene dada por la configuración del formulario

8. **Histórico de marcajes**: ¿Se debe mantener un histórico de todos los marcajes realizados por el tramitador, incluso los eliminados/modificados? ¿Para auditoría?
**Respuesta**: No, en absoluto

9. **Validaciones de negocio**: ¿Existen validaciones sobre qué campos se pueden marcar? Por ejemplo, ¿se puede marcar un campo que ya está correctamente cumplimentado?
**Respuesta**: No, se puede marcar cualquiera

10. **Permisos y roles**: ¿Todos los funcionarios tramitadores tienen permisos para marcar campos en cualquier expediente o existe alguna restricción por tipo de trámite, organismo, etc.?
**Respuesta**: No hay gestión de roles ni permisos

### Prioridad Baja

11. **Estadísticas y reporting**: ¿Se requiere información estadística sobre qué campos son más frecuentemente marcados para subsanación? ¿Para mejorar formularios?
**Respuesta**: No aplican estadísticas a nivel general en la aplicación

12. **Plantillas de motivos**: ¿Sería útil tener plantillas o textos predefinidos de motivos frecuentes para agilizar el trabajo del tramitador?
**Respuesta**: No aplica.

## SUPUESTOS

### Sobre el alcance del proyecto

**SUPUESTO 1**: El marcaje de documentos a subsanar no está incluido en el scope de Toolkit Berria y se gestiona completamente desde otros aplicativos externos (asumido según indicación del usuario).

**SUPUESTO 2**: La redacción del texto del requerimiento formal y su envío al ciudadano no son parte del scope de este proyecto (asumido según indicación del usuario).

**SUPUESTO 3**: La generación de notificaciones al ciudadano se realiza desde otro sistema externo que consume la información de campos marcados (asumido según indicación del usuario).

### Sobre el proceso del tramitador

**SUPUESTO 4**: El tramitador accede al expediente desde el sistema de tramitación (backoffice) que está integrado con el sistema donde se guardan los campos marcados.

**SUPUESTO 5**: El tramitador puede visualizar todos los campos del formulario original presentado por el ciudadano, incluyendo los valores introducidos.

**SUPUESTO 6**: El tramitador puede marcar múltiples campos en una misma sesión de trabajo sobre un expediente.

**SUPUESTO 7**: Cada campo marcado debe tener obligatoriamente un motivo textual introducido por el tramitador.

### Sobre el almacenamiento y datos

**SUPUESTO 8**: Los campos marcados se almacenan en una base de datos relacional accesible por los sistemas que lo requieran (Orquestador, sistema de tramitación, etc.).

**SUPUESTO 9**: Cada campo marcado se vincula unívocamente al expediente mediante el número de expediente o identificador único.

**SUPUESTO 10**: Los campos marcados persisten en el sistema hasta que el ciudadano complete la subsanación o expire el plazo (gestionado por otros sistemas).

### Sobre la interfaz y experiencia del tramitador

**SUPUESTO 11**: La interfaz de marcaje de campos se integra dentro del sistema de tramitación existente, no es una aplicación independiente.

**SUPUESTO 12**: El tramitador puede guardar borradores de campos marcados y retomar el trabajo posteriormente antes de confirmar definitivamente.

**SUPUESTO 13**: Una vez confirmados y guardados, los campos marcados no pueden ser modificados por el tramitador (cualquier cambio requeriría proceso diferente o permisos especiales).

## Decisiones pendientes

### Técnicas

1. **Arquitectura de integración**: Definir específicamente cómo se integra el marcaje de campos con el sistema de tramitación existente (API REST, servicios SOAP, acceso directo a BD, etc.).
**Respuesta**: No aplica a nivel general en la definición funcional de épicas e historias

2. **Modelo de datos**: Definir el esquema completo de la tabla/entidad que almacenará los campos marcados (columnas, tipos, relaciones, índices).
**Respuesta**: No aplica. Será una tarea técnica.

3. **Autenticación y autorización**: Definir cómo se valida que el usuario es un tramitador autorizado y qué permisos específicos tiene.
**Respuesta**: Únicamente, comprobar que el usuario tiene una sesión de XLNets válida

### Funcionales

4. **Flujo de confirmación**: Definir si existe un paso de "confirmación final" del marcaje de campos antes de que se procese el requerimiento, o si cada guardado es definitivo.
**Respuesta**: No es necesario.

5. **Notificación interna**: Definir si el sistema debe notificar a otros roles o sistemas cuando un tramitador ha completado el marcaje de campos de un expediente.
**Respuesta**: No es necesario

6. **Gestión de errores**: Definir qué ocurre si falla el guardado de campos marcados (reintentos automáticos, notificación al tramitador, log de errores, etc.).
**Respuesta**: Se muestra la pantalla genérica de error de la aplicación.

---

*Documento creado: 27/01/2026*  
*Última actualización: 27/01/2026*

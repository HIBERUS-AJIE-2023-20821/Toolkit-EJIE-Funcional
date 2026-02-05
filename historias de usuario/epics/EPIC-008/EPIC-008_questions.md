# EPIC-008: Preguntas y Supuestos

## Preguntas abiertas

### P1: Formato y estructura de XML de apilamiento
¿Cuál es la estructura exacta de los archivos XML que envía Mi Carpeta? ¿Existe un esquema XSD definido para validar el contenido?
***Respuesta***: El análisis de estos XML formarán parte de una tarea técnica

### P2: Gestión de múltiples requerimientos
Si un ciudadano tiene varios requerimientos de subsanación pendientes para el mismo expediente, ¿cómo se gestionan? ¿Se acumulan en una única subsanación o son procesos independientes?
***Respuesta***: Sólo hay un requerimiento de subsanación por expediente

### P3: Plazo de subsanación
¿Se muestra al ciudadano el plazo límite para completar la subsanación? ¿Qué ocurre si el plazo vence durante el proceso de subsanación?
***Respuesta***: En el documento notificado aparecerá el plazo de subsanación. En el caso de que venza, será Mi Carpeta quién eliminará el enlace y no se podrá continuar con el requerimiento.

### P4: Recuperación de subsanación en progreso
¿Puede el ciudadano guardar progreso y volver posteriormente a continuar la subsanación? ¿Cómo accede nuevamente si ya está en proceso?
***Respuesta***: Mientras no se termine y presente, queda guardado como borrador. Sólo es posible tener un borrador por expdiente y usuario. Cuando el usuario accede desde MiCarpeta ToolkitBerria comprobará la existencia de dicho borrador anterior para presentárselo y permitirle continuar con él.

### P5: Visualización de motivo de requerimiento
¿Se muestra al ciudadano el motivo específico por el que el tramitador ha marcado cada campo para subsanar? ¿Hay comentarios o explicaciones adicionales?
***Respuesta***: No, toda esa información estará incluida en el documento de requerimiento. No aplica a ToolkiBerria

### P6: Campos condicionantes no marcados
Si un campo condicionante NO está marcado para subsanar pero el ciudadano modifica otro campo que también condiciona elementos, ¿cómo se gestionan los conflictos de condicionamiento?
***Respuesta***: Se activan todos los componentes que puedan estar condicionados por un campo que sí está marcado como "a subsanar" permitiendo ejecutar la condición y/o validación

### P7: Documentos previamente cargados
Si un documento fue cargado en la solicitud original y ahora debe modificarse por condicionamiento, ¿se reemplaza, se añade uno nuevo, o se gestionan versiones?
***Respuesta***: El paso de Autorizaciones, Documentos y Declaraciones Responsables muestra la información configurada en el CCP para el procedimiento y acción telemática. NO se muestran estos elementos de la solicitud. el ciudadano tendrá que completar e incluir aquellos documentos que se le hayan solicitado subsanar en el documento de requerimiento adjunto a la notificación. 

### P8: Validaciones específicas de subsanación
¿Existen validaciones específicas diferentes en subsanación respecto a la solicitud original? ¿Pueden relajarse ciertas validaciones?
***Respuesta***: Por regla general, el formulario de datos (paso Datos Específicos) debería ser idéntico a la solicitud. En el resto de pasos, según configuración en CCP.

### P9: Notificación tras envío
¿Se notifica al ciudadano por algún canal (email, SMS) confirmando el envío de la subsanación? ¿Se genera algún tipo de acuse de recibo?
***Respuesta***: Al igual que en la solicitud, cuando se presenta y registra la subsanación el ciudadano recibe un justificante que también recibe por correo electrónico.

### P10: Histórico de subsanaciones
¿Puede el ciudadano consultar el histórico de subsanaciones realizadas sobre un mismo expediente? ¿Dónde se visualiza este histórico?
***Respuesta***: En Mi Carpeta se refleja toda la historia del expediente. No aplica a Toolkit Berria

### P11: Interesados múltiples
Si la solicitud original tenía múltiples interesados, ¿quién puede realizar la subsanación? ¿Todos los interesados o solo el solicitante principal?
***Respuesta***: El interesado a efectos de la ley, el representante si existiera o cualquier autorizado de ambos roles en líneas generales. 

### P12: Firma múltiple en subsanación
Si la solicitud original requirió firma múltiple, ¿la subsanación también requiere firma de todos los interesados o solo del que subsana?
***Respuesta***: 

### P13: Modificación de interesados
¿Se permite modificar datos de interesados en la subsanación o solo datos específicos del procedimiento?
***Respuesta***: NO, no se permite modificar información de los interesados ni de los datos de notificación.

### P14: Caducidad del borrador
¿El borrador de subsanación generado por el tramitador tiene fecha de caducidad? ¿Qué ocurre si el ciudadano no accede nunca a subsanar?
***Respuesta***: El proceso de purgado será el encargado de eliminarlo

---

## Supuestos

### S1: Acceso exclusivo desde Mi Carpeta
Se asume que el único punto de acceso a subsanaciones es Mi Carpeta, no existiendo acceso directo mediante URL o enlaces externos.

### S2: Un requerimiento a la vez
Se asume que el ciudadano solo puede trabajar en un requerimiento de subsanación a la vez por expediente, completándolo antes de recibir otro.

### S3: Preservación de estructura
Se asume que la subsanación mantiene la misma estructura de pasos que la solicitud original, sin añadir ni eliminar pasos.

### S4: Condicionamientos configurados previamente
Se asume que todas las reglas de condicionamiento entre campos, documentos y declaraciones están configuradas en el procedimiento y no se crean dinámicamente.

### S5: Validaciones iguales a solicitud original
Se asume que las validaciones de negocio aplicadas en subsanación son las mismas que en la solicitud original, sin variaciones.

### S6: Firma obligatoria
Se asume que toda subsanación requiere firma electrónica del ciudadano, sin posibilidad de envío sin firma.

### S7: Guardado automático
Se asume que el sistema guarda automáticamente los cambios realizados mientras el ciudadano trabaja en la subsanación, similar a borradores.

### S8: Unicidad de modificación
Se asume que si un campo es modificado, el nuevo valor reemplaza completamente el anterior sin mantener histórico visible para el ciudadano.

### S9: Documentos en Dokusi
Se asume que los documentos cargados en subsanación se almacenan en Dokusi y se relacionan con el expediente del mismo modo que en solicitud original.

### S10: Justificante inmediato
Se asume que el justificante de subsanación se genera inmediatamente tras el envío y está disponible para descarga sin demora.

### S11: No modificación de paso 1
Se asume que el paso de identificación/interesados no es modificable en subsanación, siendo estos datos inmutables una vez creada la solicitud.

### S12: Sincronización con tramitador
Se asume que el sistema tramitador recibe notificación inmediata cuando se completa una subsanación para continuar la tramitación.

### S13: Campos dependientes en cascada
Se asume que los campos dependientes pueden tener a su vez dependientes, creando cadenas de condicionamiento que se resuelven correctamente.

### S14: Documentos opcionales no requeridos
Se asume que los documentos opcionales en la solicitud original siguen siendo opcionales en subsanación salvo que condicionamiento los haga obligatorios.

---

## Decisiones pendientes

### D1: Estrategia de navegación forzada
Decidir si el ciudadano debe navegar secuencialmente por todos los pasos o puede saltar directamente a los pasos con elementos marcados para subsanar.

### D2: Resumen inicial de elementos pendientes
Definir si se muestra una pantalla inicial de resumen con todos los elementos marcados antes de acceder a los pasos del formulario.

### D3: Indicadores de progreso
Establecer cómo se indica al ciudadano qué elementos ha completado y cuáles quedan pendientes durante el proceso de subsanación.

### D4: Gestión de timeouts
Definir comportamiento si la sesión expira durante la subsanación: ¿se pierde progreso, se guarda automáticamente, se permite recuperar?

### D5: Logs de trazabilidad
Establecer qué nivel de detalle se registra en logs sobre qué campos fueron modificados, qué valores tenían antes y después, y quién realizó los cambios.

---

*Documento creado: 29/01/2026*

# EPIC-007: Preguntas y Supuestos

## Preguntas abiertas

### P1: Validación de datos mínimos para guardar presolicitud
¿Cuáles son los datos mínimos obligatorios que debe completar el ciudadano antes de poder guardar la presolicitud? ¿Es obligatorio rellenar todos los pasos o puede guardarse con información parcial?

***Respuesta***: Cada paso controlará qué datos son obligatorios

### P2: Tiempo de persistencia de presolicitudes
¿Cuánto tiempo permanece una presolicitud almacenada en el sistema antes de su caducidad? ¿Existe algún mecanismo de limpieza automática de presolicitudes no utilizadas?

***Respuesta***: Habrá un proceso de purgado y borrado de solicitudes (no es objeto de estta épica)

### P3: Acceso a presolicitudes guardadas
¿Puede el ciudadano recuperar y consultar una presolicitud previamente guardada desde otro equipo o sesión? ¿Cómo identificaría su presolicitud sin autenticación?

***Respuesta***: No. Una vez finalizada, el ciudadano no puede volver a ella. Los datos se quedan almacenados para que la continue finalice el tramitador. Pero esto es objeto de otra épica.

### P4: Límite de documentos en modo presencial
¿Existe alguna limitación específica en el número o tamaño total de documentos que puede cargar un ciudadano en modo presencial? ¿Difiere de los límites de tramitación telemática estándar?

***Respuesta***: Mismas limitaciones que en la tramitación estándar

### P5: Gestión de errores en servicio Dokusi
Si el servicio de Dokusi para generar el código QR no está disponible, ¿cuál es el comportamiento esperado? ¿Se bloquea el guardado de la presolicitud o se ofrece alternativa?

***Respuesta***: Permitir el reintento de la operación de finalización. Si no se genera el QR, la solicitud no se finaliza.

### P6: Formato de descarga del QR individual
Cuando el ciudadano descarga "solo QR", ¿qué formato debe tener el archivo? ¿Imagen PNG/JPG, PDF reducido, o ambas opciones disponibles?

***Respuesta***: Solo QR descargará una imagen con el QR en formato PNG/JPEG

### P7: Impresión directa desde pantalla de éxito
¿Debe ofrecerse opción de impresión directa desde la pantalla de éxito, además de las descargas?

***Respuesta***: No, solo descarga. La impresión la realizará a posteriori el usaurio.

### P8: Notificaciones o recordatorios
¿Se envía alguna notificación por email o SMS al ciudadano con el código de presolicitud? En modo sin autenticación, ¿cómo se obtendría contacto del ciudadano?

***Respuesta***: No procede envío de notificación/recordatorio

### P9: Modificación de presolicitudes
¿Puede el ciudadano modificar una presolicitud después de haberla guardado? Si es así, ¿cómo accedería a ella sin autenticación?

***Respuesta***: No. Este tipo de solicitudes no son recuperables. No tienen borradores ni plantillas.

### P10: Versionado de presolicitudes
Si un ciudadano guarda varias presolicitudes del mismo procedimiento en diferentes sesiones, ¿todas quedan disponibles o la última sobrescribe las anteriores?

***Respuesta***: No. no procede versionado.

### P11: Tipos de procedimientos permitidos
¿Todos los procedimientos del Gobierno Vasco permiten tramitación presencial ciudadanía o solo un subconjunto específico? ¿Cómo se configura esta habilitación?

***Respuesta***: La configuración estará en el CCP

### P12: Validación del tipo de presentación en configuración
¿El parámetro tipoPresentación=19 puede ser manipulado por usuarios externos o solo puede establecerse desde URLs oficiales? ¿Existe validación de origen?

***Respuesta***: El enlace estará desde el portal de euskadi.eus, ficha del procedimento en cuestión.

### P13: Integración con sistemas de gestión de colas
¿Se integra el proceso de presencial ciudadanía con sistemas de gestión de colas de oficinas públicas? ¿El código de presolicitud sirve para asignar prioridad o turno?

***Respuesta***: No. No procede.

---

## Supuestos

### S1: Acceso configurado con tipo presentación
Se asume que el acceso a formularios presenciales se realiza mediante URLs configuradas que incluyen el parámetro tipoPresentación=19.

### S2: Conexión estable durante la sesión
Se asume que el ciudadano dispone de conexión estable durante todo el proceso de rellenado. El sistema implementa guardado automático para mitigar desconexiones temporales.

### S3: Documentos físicos complementarios
Se asume que el ciudadano puede presentar documentación física adicional no cargada digitalmente cuando acude presencialmente a las oficinas.

### S4: Sin autenticación durante todo el flujo
Se asume que el proceso completo del ciudadano en modo presencial no requiere autenticación en ningún momento, ni siquiera para consultar o modificar presolicitudes.

### S5: Unicidad del código QR
Se asume que el código de presolicitud generado es único e irrepetible, garantizando que cada presolicitud tiene identificador distinto.

### S6: Disponibilidad del servicio Dokusi
Se asume disponibilidad estándar del servicio de Dokusi para generación de QR. En caso de indisponibilidad, se documenta alternativa en gestión de errores.

### S7: Sin límite temporal durante rellenado
Se asume que el ciudadano puede tomar el tiempo que necesite para rellenar el formulario sin límite de sesión mientras permanece activo en el navegador.

### S8: Formato PDF estándar
Se asume que el PDF generado cumple con estándares de accesibilidad y es compatible con visores y lectores de PDF estándar.

### S9: Limpieza automática del navegador
Se asume que al cerrar el navegador, los datos temporales se limpian automáticamente por configuración del navegador.

### S10: Modalidad solo para personas físicas
Se asume explícitamente que presencial ciudadanía solo aplica a tramitaciones de personas físicas sin representación mediante registro de apoderamientos.

### S11: No requiere prerrellenado automático
Se asume que en modo presencial no se invocan servicios de prerrellenado automático de datos, ya que no hay certificado digital del que extraer información.

### S12: Documentos no obligatorios son opcionales
Se asume que el ciudadano puede optar por no cargar documentos digitalmente y presentarlos todos físicamente en las oficinas.

---

## Decisiones pendientes

### D1: Estrategia de recuperación de presolicitudes
Definir si el ciudadano puede o no recuperar presolicitudes guardadas desde diferentes sesiones, y en caso afirmativo, qué mecanismo de identificación se utiliza sin autenticación.

### D2: Política de caducidad
Establecer política de retención y caducidad de presolicitudes: tiempo de almacenamiento, proceso de limpieza, notificaciones previas a eliminación.

### D3: Gestión de errores críticos
Definir comportamiento del sistema ante fallos en servicios críticos (Dokusi, almacenamiento, generación de PDF) durante el guardado de presolicitud.

### D4: Accesibilidad de documentos generados
Validar que PDFs y códigos QR generados cumplen con requisitos de accesibilidad y normativa de Gobierno Vasco.

---

*Documento creado: 29/01/2026*

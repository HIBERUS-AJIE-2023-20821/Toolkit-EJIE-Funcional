# EPIC-007: Presencial Ciudadanía - Proceso del Ciudadano

## Resumen / Objetivo
Permitir que el ciudadano inicie una solicitud presencial sin necesidad de autenticación, rellene el formulario y documentos, y genere una solicitud con código QR para ser presentada ante un tramitador, facilitando la tramitación presencial con información precargada.

## Descripción funcional
Las solicitudes presenciales permiten al ciudadano iniciar una tramitación telemática que será completada presencialmente en oficinas de la Administración. El ciudadano puede rellenar el formulario sin autenticarse, guardar la información, y obtener un PDF con código QR que identificará su solicitud.

La solicitud presencial generada contiene todos los datos y documentos aportados por el ciudadano. Los documentos se almacenan en Dokusi y quedan relacionados con la solicitud. El código QR permite al tramitador recuperar esta información de forma inmediata al escanearla.

El ciudadano accede al formulario con un tipo de presentación específico (tipoPresentación=19) que activa el modo presencial. La habilitación de esta modalidad para cada procedimiento se configura en el CCP (Catálogo de Configuración de Procedimientos). En este modo, el sistema no solicita firma electrónica ni permite el envío directo de la solicitud. En su lugar, al finalizar, genera un PDF con el código QR integrado y los datos de identificación de la solicitud presencial.

El QR contiene el código del servicio, los dígitos del procedimiento y el identificador único de la solicitud. El ciudadano puede descargar el PDF completo o solo el código QR para presentarlo posteriormente en las oficinas junto con la documentación física que considere necesaria.

## Historias relacionadas
- [US-025](US-025.md) - Acceso sin autenticación para presencial ciudadanía
- [US-026](US-026.md) - Rellenado de formulario y carga de documentos
- [US-027](US-027.md) - Guardado de solicitud presencial y asignación de código
- [US-028](US-028.md) - Generación de PDF con código QR integrado
- [US-029](US-029.md) - Descarga y presentación de solicitud presencial

---

*Épica creada: 29/01/2026*

# EPIC-008: Subsanación - Proceso del Ciudadano

## Resumen / Objetivo
Permitir que el ciudadano que ha recibido un requerimiento de subsanación acceda a su solicitud desde Mi Carpeta y corrija los datos y documentos señalados por el tramitador, completando correctamente su expediente para continuar con la tramitación.

## Descripción funcional
El proceso de subsanación se inicia cuando el ciudadano recibe una notificación de requerimiento. Desde Mi Carpeta, el ciudadano accede al proceso de subsanación en el sistema mediante el botón "Subsanar" que se activa tras la notificación.

El sistema carga la información de subsanación en estado borrador generada por el tramitador. El paso 2 (datos específicos) se precarga con los datos de la solicitud original, mostrando solo editables los campos específicamente marcados por el tramitador para subsanar. Los campos no marcados se muestran en solo lectura.

Los demás pasos (documentos, declaraciones, autorizaciones, etc.) se cargan según la configuración del CCP (Catálogo de Configuración de Procedimientos) para la acción telemática de subsanación y deben ser completados por el ciudadano. Estos pasos pueden incluir:
- Autorizaciones de consulta de datos
- Documentos específicos requeridos para la subsanación
- Declaraciones responsables necesarias

Los campos en el paso 2 pueden tener dependencias: al modificar un campo condicionante marcado para subsanar, se habilitan automáticamente los campos dependientes según las reglas configuradas.

El acceso desde Mi Carpeta se realiza mediante apilamiento remoto, enviando archivos XML con los parámetros necesarios (procedimiento, acción telemática, expediente, datos de interesados) que el sistema utiliza para contextualizar correctamente la subsanación.

Una vez el ciudadano completa las correcciones requeridas y los pasos configurados, debe firmar y enviar la subsanación. El sistema valida que todos los elementos obligatorios estén completados antes de permitir el envío final.

## Historias relacionadas
- [US-030](US-030.md) - Acceso a subsanación desde Mi Carpeta
- [US-031](US-031.md) - Carga de paso 2 con datos de solicitud original
- [US-032](US-032.md) - Edición condicional de campos en datos específicos
- [US-033](US-033.md) - Completado de documentos según configuración CCP
- [US-034](US-034.md) - Completado de declaraciones según configuración CCP
- [US-035](US-035.md) - Validación, firma y envío de subsanación

---

*Épica creada: 29/01/2026*

# EPIC-001: Subsanación - Proceso del Ciudadano

## ID
EPIC-001

## Título
Subsanación - Proceso del Ciudadano

## Resumen / Objetivo
Permitir a los ciudadanos responder a requerimientos de subsanación de manera electrónica, aportando documentación o datos faltantes/incorrectos identificados por el tramitador, reduciendo tiempos de tramitación y mejorando la experiencia del usuario en la tramitación telemática.

## Descripción funcional
Abarca el flujo completo de tramitación electrónica de subsanaciones que permite a un ciudadano (o su representante, ya sea con apoderamiento registrado o con representación específica establecida en la solicitud inicial) acceder a un requerimiento de subsanación, aportar la información o documentación solicitada por el funcionario tramitador y enviar la respuesta a la Administración para continuar con la tramitación del expediente.

El proceso incluye: acceso mediante enlace con parámetros, recuperación de configuración, renderizado del formulario asociado, identificación de participantes (interesado/representante/autorizado), edición de campos marcados para subsanación, aplicación de validaciones en tiempo real, gestión de documentos con almacenamiento y código QR, gestión de declaraciones responsables, generación de resumen, creación de PDF justificante y envío al sistema de gestión con registro de auditoría completo.

Los participantes y su tipo de representación ya están definidos en el expediente original. Durante la subsanación, el sistema verifica permisos pero no permite cambiar la representación establecida.

Este proceso NO requiere paso de identificación de interesados (ya definidos en expediente), NO requiere firma electrónica (solo autenticación), solo se editan campos específicos marcados por tramitador, se muestran valores previos a corregir, y se asocia a expediente existente.

## Historias relacionadas
- US-001: Acceso al proceso de subsanación e identificación del requerimiento
- US-002: Visualización de datos del expediente y participantes
- US-003: Edición de campos requeridos para subsanación
- US-004: Gestión de documentos requeridos para subsanación
- US-005: Gestión de declaraciones responsables
- US-006: Pantalla de resumen de la subsanación
- US-007: Generación de PDF justificante y envío

---

*Épica creada: 26/01/2026*  
*Última actualización: 26/01/2026*  
*Estado: Planificada*

# EPIC-004: Paso 4 - Documentos Ajustes de configuración

## ID
EPIC-004

## Título
Paso 4 - Documentos Ajustes de configuración

## Resumen / Objetivo
Permitir que el sistema adapte dinámicamente la gestión y visualización de documentos en el paso 4 según la configuración establecida en el catálogo de procedimientos, garantizando que el ciudadano solo pueda aportar documentos conforme a las reglas definidas para cada procedimiento.

## Descripción funcional
En el proceso de tramitación electrónica, el paso 4 - Documentos debe comportarse de forma flexible según las reglas de negocio configuradas en el CCP (Catálogo de Configuración de Procedimientos). Esta épica aborda tres aspectos críticos de configuración documental:

**Limitación de unicidad de documento**: Controlar que solo se pueda aportar un único documento por tipo cuando así esté configurado, independientemente del origen (desde dispositivo, documentos entregados anteriormente o mis documentos). Si el procedimiento limita a un único documento por tipo, el sistema debe impedir añadir más de uno mediante cualquier vía de aportación.

**Visualización condicional de "Otros Documentos"**: Mostrar u ocultar la sección de "Otros Documentos" según lo permita la configuración del procedimiento. Si el catálogo indica que no se pueden adjuntar otros documentos, esta opción no debe mostrarse al ciudadano en el paso 4.

**Formatos específicos por tipo de documento**: Informar al ciudadano sobre los formatos específicos permitidos para cada tipo de documento requerido. Algunos documentos requieren formatos (extensiones) concretas que se encuentran configuradas en el catálogo y deben mostrarse visualmente al ciudadano, además de validarse durante la carga.

El sistema debe recuperar la configuración del catálogo de procedimientos y adaptar dinámicamente el comportamiento y visualización del paso 4 según las reglas establecidas.

## Historias relacionadas
- US-015: Limitación de unicidad de documento por tipo
- US-016: Visualización condicional del bloque "Otra documentación"
- US-017: Visualización de formatos específicos por tipo de documento

---

*Épica creada: 28/01/2026*  
*Última actualización: 28/01/2026*

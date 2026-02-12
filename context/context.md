# Project Context - ToolkitBerria

## 1. Resumen del producto/proyecto
- **Nombre del proyecto**: Toolkit Berria ASI (Atención a los Servicios de Información)
- **Cliente/Organización**: EJIE - Sociedad Informática del Gobierno Vasco
- **Propósito general**: Modernizar y centralizar la creación y gestión de formularios electrónicos de la Administración, facilitando la tramitación telemática completa de procedimientos administrativos del Gobierno Vasco. El sistema permite a la ciudadanía presentar solicitudes, subsanaciones, aportaciones y justificaciones de forma electrónica, con soporte para firma simple y múltiple, multiinteresados y representación.
- **Componentes principales**:
  - **EraiKIT (Compositor de Formularios)**: Herramienta de diseño y configuración de formularios dinámicos
  - **Orquestador**: Sistema de ejecución que gestiona el flujo completo de tramitación
- **Objetivos clave**:
  - Modernizar la creación y gestión de formularios electrónicos de la Administración
  - Centralizar en un catálogo único todos los formularios reutilizables
  - Facilitar la tramitación telemática completa (solicitudes, subsanaciones, aportaciones, justificaciones)
  - Permitir firma múltiple y gestión de multiinteresados en solicitudes
  - Reducir los tiempos de tramitación mediante procesos electrónicos orquestados
  - Mejorar la experiencia del usuario con formularios dinámicos y prerrellenado automático
  - Garantizar la trazabilidad completa de todos los procesos
  - Integrar con los sistemas corporativos existentes del Gobierno Vasco (CCP, RdA, Dokusi, GILTZA, PPS, XLNET)

## 2. Alcance

### 2.1 IN (incluido)
- **Compositor de Formularios (EraiKIT)**:
  - Diseño visual de formularios mediante compositor gráfico
  - Gestión del catálogo centralizado de formularios
  - Versionado de formularios (versión mayor para cambios estructurales, release menor para cambios de contenido)
  - Catálogo de SVTs (Servicios de Validación de Terceros) para integraciones con servicios departamentales
  - Gestión de grupos funcionales (PLATEA-Tramitación y grupos departamentales)
  - Configuración de componentes con validaciones y prerrellenado automático
  - Estados de formularios: Borrador → Publicado
  - Ayudas contextuales y guías interactivas para configuradores
  
- **Orquestador**:
  - **Gestión de solicitudes**: Creación, modificación, envío y consulta de solicitudes
  - **Gestión de borradores**: Guardado automático y manual, recuperación por ciudadano
  - **Gestión de interesados**: Solicitudes "Para mí" (solicitante único), "Para otro" (con representación específica), multiinteresados
  - **Proceso de firma**: Firma simple y firma múltiple con notificaciones por email
  - **Representación**: Gestión de representados mediante RdA (Registro de Apoderamientos)
  - **Prerrellenado automático**: Invocación de SVTs para autocompletar campos
  - **Validaciones en tiempo real**: Formato de datos, coherencia de información
  - **Gestión documental**: Carga, validación y almacenamiento de documentos en Dokusi
  - **Declaraciones responsables**: Presentación, aceptación y registro con auditoría
  - **Generación de justificantes**: PDF resumen de la solicitud
  - **Envío y registro**: Integración con PPS para registro oficial de solicitudes
  
- **Tipos de acciones telemáticas soportadas**:
  - Solicitudes iniciales
  - Subsanaciones de expedientes
  - Aportaciones de documentación
  - Justificaciones

- **Trazabilidad y auditoría**: Registro completo de todas las acciones del usuario con fecha/hora, IP y usuario

### 2.2 OUT (excluido)
- **Compositor de Formularios**:
  - Ejecución de formularios en tiempo real (responsabilidad del Orquestador)
  - EraiKIT solo disponible en entorno de desarrollo
  - Traspaso a otros entornos gestionado por CCP mediante proceso PIF
  
- **Orquestador**:
  - Creación y configuración de procedimientos administrativos (gestionado en CCP)
  - Autenticación del usuario (gestionada por XLNET/GILTZA)
  - Gestión de apoderamientos y representantes (gestionada por RdA)
  - Registro de interesados (gestionado por RI - Registro de Interesados)
  - Almacenamiento de documentos (gestionado por Dokusi)
  - Firma electrónica (componente GILTZA/Izenpe)
  - Registro oficial de solicitudes (gestionado por PPS)
  - Tramitación posterior del expediente por funcionarios (backoffice de tramitación)
  - Análisis antivirus de documentos (opcional, gestionado por infraestructura)
  - Consulta de solicitudes enviadas desde otros canales (antiguo Toolkit, envíos directos a PPS)

## 3. Usuarios, roles y permisos

### Roles principales

- **Configurador de formularios** (EraiKIT):
  - Técnico de EJIE o departamental que diseña formularios en EraiKIT
  - Accede solo en entorno de desarrollo
  - Puede crear, modificar y publicar formularios
  - Gestiona SVTs y sus configuraciones
  - Organiza formularios por grupos funcionales
  
- **Gestor de procedimientos** (CCP):
  - Administrador que configura procedimientos en el CCP
  - Asocia formularios (versiones específicas) a acciones telemáticas
  - Coordina el traspaso de formularios entre entornos mediante PIF
  - Define configuración de firma, multifirma, multiinteresado, prerrellenado
  
- **Ciudadano/Interesado**: 
  - Persona física o jurídica que presenta solicitudes o responde a requerimientos
  - Puede cumplimentar formularios, guardar borradores, firmar y enviar solicitudes
  - Puede actuar "Para mí" o "Para otro" (con representación específica)
  - Accede mediante autenticación del Gobierno Vasco (XLNET/GILTZA)
  
- **Representante con apoderamient RdA**: 
  - Persona que actúa en nombre de un representado con apoderamiento registrado en RdA
  - Puede presentar solicitudes en nombre de sus representados
  - NO puede usar apoderamientos RdA para solicitudes "Para otro" (requiere representación específica)
  - El sistema identifica automáticamente los representados desde RdA
  
- **Autorizado de empresa** (RdA):
  - Persona física autorizada por una empresa (persona jurídica) en RdA
  - Puede presentar solicitudes en nombre de la empresa
  - El sistema identifica automáticamente las empresas autorizadoras desde RdA

- **Multiinteresado/Firmante**:
  - Persona que participa en una solicitud con firma múltiple
  - Recibe notificación por email para acceder, revisar y firmar
  - Puede firmar o rechazar (con motivo obligatorio) la solicitud
  - Email obligatorio para notificaciones
  
- **Funcionario tramitador** (fuera del alcance de Toolkit Berria, pero relevante para contexto):
  - Revisa las solicitudes recibidas en el sistema de tramitación
  - Marca campos y documentos que requieren subsanación
  - Gestiona el expediente completo desde PPS/sistema de tramitación

### Permisos

- **Configurador de formularios**:
  - Crear formularios en borrador
  - Modificar formularios en borrador (no publicados)
  - Publicar formularios (solo si SVTs asociados están en estado "Publicado")
  - Crear y modificar SVTs de su grupo funcional
  - Consultar formularios y SVTs de grupo PLATEA-Tramitación
  - No puede modificar formularios publicados (debe crear nueva versión/release)
  - No puede eliminar SVTs en uso
  
- **Gestor de procedimientos (CCP)**:
  - Asociar formularios a acciones telemáticas
  - Coordinar traspaso de formularios a pruebas/producción
  - Configurar parámetros de procedimientos (firma, multiinteresado, etc.)
  
- **Ciudadano/Interesado**: 
  - Acceder a formularios de procedimientos publicados
  - Cumplimentar y modificar datos (mientras no esté firmado/enviado)
  - Guardar borradores (manual y automático)
  - Adjuntar documentos según tipos configurados
  - Firmar solicitudes
  - Enviar solicitudes (acción irreversible)
  - Consultar solicitudes enviadas desde Toolkit Berria
  - No puede enviar otra solicitud si tiene una en proceso de firma múltiple
  
- **Representante/Autorizado**:
  - Mismo conjunto de acciones que el ciudadano
  - Actúa en nombre de representado/empresa autorizadora
  - El sistema registra quién realizó cada acción (interesado, representante o autorizado)
  
- **Firmante en firma múltiple**:
  - Acceder a solicitud mediante enlace en email
  - Revisar información (solo lectura)
  - Firmar o rechazar con motivo
  - NO puede modificar información del formulario

## 4. Módulos/Componentes funcionales

### EraiKIT - Compositor de Formularios (Backend de Configuración)

**Entorno**: Solo disponible en desarrollo

**Módulos principales**:

1. **Gestión de Formularios**:
   - Editor visual (compositor gráfico) para diseño de formularios
   - Versionado: Versión (cambios estructurales) y Release (cambios de contenido)
   - ID formato: `F-OOOO-NNNNNNNNN-V99` (Grupo funcional-Nombre-Versión)
   - Estados: Borrador (modificable) → Publicado (inmutable)
   - Validaciones de coherencia antes de publicación
   - No permite publicar si SVTs asociados están en estado "Mock"
   
2. **Catálogo de Formularios**:
   - Repositorio centralizado de formularios reutilizables
   - Búsqueda y filtrado por grupo funcional, nombre, versión
   - Gestión de componentes dentro de formularios
   - Configuración de validaciones y prerrellenado por componente
   
3. **Catálogo de SVTs (Servicios de Validación de Terceros)**:
   - Gestión de microservicios/APIs departamentales
   - ID formato: `SVT-OOOO-NNNNNNNNN`
   - Tipos: SOAP / REST
   - Configuración de endpoint, operación/método HTTP, parámetros de entrada
   - Esquemas de retorno: Validación, Valor simple, Lista simple, Clave-Valor, Tabla de datos
   - Estados: Mock (simulado para pruebas) → Publicado
   - Bloque de respuesta simulada para estado Mock
   - Validación de tipos de datos entre componentes y SVTs
   
4. **Gestión de Grupos Funcionales**:
   - PLATEA-Tramitación: Accesible por todos los configuradores
   - Grupos departamentales: Solo accesibles por su grupo
   - Control de permisos basado en grupo funcional
   
5. **Ayudas y Guías**:
   - Consejos contextuales durante la composición
   - Normas de configuración integradas
   - Guías interactivas para usuarios nuevos
   
6. **Servicio de Consulta** (para CCP):
   - API para consultar formularios publicados
   - Obtención de versiones y releases disponibles

### Orquestador (Backend de Ejecución)

**Entorno**: Desarrollo, Pruebas, Preproducción, Producción

**Módulos principales**:

1. **Módulo de Autenticación e Identificación**:
   - Integración con XLNET para autenticación de usuarios
   - Recuperación de datos del usuario autenticado
   - Gestión de sesiones
   
2. **Módulo de Gestión de Procedimientos** (integración con CCP):
   - Consulta de información del procedimiento
   - Obtención de configuración de acción telemática
   - Recuperación de formulario asociado (versión específica)
   - Obtención de configuración de firma, multifirma, multiinteresado, prerrellenado
   
3. **Módulo de Renderizado de Formularios**:
   - Interpretación de la configuración del formulario desde EraiKIT
   - Renderizado dinámico en frontend
   - Soporte para múltiples tipos de componentes (texto, numérico, desplegable, tabla, etc.)
   
4. **Módulo de Gestión de Interesados**:
   - Identificación del tipo de solicitud: "Para mí" / "Para otro"
   - Integración con RdA para obtener representados y empresas autorizadoras
   - Gestión de multiinteresados en firma múltiple
   - Validación de apoderamientos
   - Documentación de representación específica para "Para otro"
   
5. **Módulo de Prerrellenado Automático**:
   - Invocación de SVTs configurados
   - Autocompletado de campos con datos recuperados
   - Gestión de errores en invocaciones a SVTs
   
6. **Módulo de Validaciones**:
   - Validaciones en tiempo real durante cumplimentación
   - Validaciones de formato (NIF, IBAN, email, fechas, etc.)
   - Validaciones de negocio mediante SVTs
   - Validaciones de coherencia entre campos
   
7. **Módulo de Gestión de Borradores**:
   - Guardado automático periódico
   - Guardado manual por el usuario
   - Recuperación de borradores por ciudadano
   - Filtrado por tipo: Para mí / Como representante / Como autorizado
   - Solo se mantiene el borrador más reciente por solicitud
   
8. **Módulo de Gestión Documental** (integración con Dokusi):
   - Carga de archivos (selección y drag & drop)
   - Validación de formato y tamaño
   - Almacenamiento en Dokusi con metadatos
   - Generación de QR para documentos
   - Eliminación de documentos antes del envío
   
9. **Módulo de Declaraciones Responsables**:
   - Presentación de declaraciones configuradas en CCP
   - Gestión de aceptación con checkboxes
   - Registro de fecha/hora/IP de aceptación
   - Diferenciación entre obligatorias y opcionales
   
10. **Módulo de Firma** (integración con GILTZA):
    - **Firma simple**: Un único firmante
    - **Firma múltiple**: 
      - Propietario firma y bloquea el formulario
      - Envío de emails a interesados firmantes
      - Acceso mediante enlace para revisar y firmar/rechazar
      - Gestión de rechazos con motivo obligatorio
      - Registro automático cuando todos firman
      - Notificaciones por email en cada firma
    - Componente GILTZA Ciudadano y GILTZA Profesional
    
11. **Módulo de Resumen y Confirmación**:
    - Generación de pantalla de resumen con toda la información
    - Navegación a pasos anteriores para correcciones
    - Confirmación antes del envío
    
12. **Módulo de Generación de Justificantes**:
    - Generación de PDF resumen de la solicitud
    - Inclusión de: datos del procedimiento, interesados, datos cumplimentados, documentos adjuntos, declaraciones aceptadas, fecha/hora, número de registro
    - Almacenamiento del PDF en Dokusi
    
13. **Módulo de Envío y Registro** (integración con PPS):
    - Preparación del payload ejgvDocument (datos de tramitación + datos de negocio)
    - Envío al sistema PPS para registro oficial
    - Gestión de reintentos ante errores
    - Generación de número de registro único
    - Notificaciones de confirmación por email
    
14. **Módulo de Consulta de Solicitudes**:
    - Servicio getRequestInformation para consultar solicitudes enviadas
    - Solo solicitudes enviadas desde Toolkit Berria
    - Devuelve ejgvDocument completo (tramitación + negocio)
    
15. **Módulo de Plantillas** (integración con Toolkit-Plantillas):
    - Guardado de plantillas para reutilización
    - Recuperación de plantillas guardadas

### Integración entre componentes

```
EraiKIT (desarrollo)
    ↓ Traspaso vía PIF
CCP (todos los entornos)
    ↓ Consulta de formularios
Orquestador (todos los entornos)
    ↓ Renderizado y ejecución
Ciudadano (frontend)
```

### Backoffice (fuera del alcance de Toolkit Berria)

- **Sistema de Tramitación**: Gestión de expedientes por funcionarios
- **Marcado de subsanaciones**: Identificación de campos y documentos a subsanar
- **Recepción desde PPS**: Solicitudes registradas para tramitación

## 5. Procesos de negocio (alto nivel)

### Proceso 1: Configuración de Formularios en EraiKIT

**Actores**: Configurador de formularios, EraiKIT, CCP

**Estados**: Borrador → Publicado

**Flujo principal**:

1. **Creación del formulario**
   - Configurador accede a EraiKIT (solo en desarrollo)
   - Crea nuevo formulario o nueva versión/release de uno existente
   - Asigna ID: F-OOOO-NNNNNNNNN-V99
   - Selecciona grupo funcional

2. **Composición visual**
   - Añade componentes mediante editor gráfico
   - Configura propiedades de cada componente
   - Asocia SVTs para validación y/o prerrellenado
   - Define validaciones de campos

3. **Gestión de SVTs**
   - Crea SVTs en catálogo si no existen
   - Configura endpoint, tipo (SOAP/REST), parámetros, esquema de retorno
   - Prueba SVT en estado Mock
   - Publica SVT cuando está listo

4. **Publicación del formulario**
   - Valida coherencia de configuración
   - Verifica que todos los SVTs asociados estén en estado "Publicado"
   - Publica formulario (pasa a estado inmutable)

5. **Traspaso a otros entornos**
   - CCP coordina traspaso mediante proceso PIF
   - Se traspasa versión + releases + SVTs asociados
   - Si versión ya existe en destino, no se actualiza

### Proceso 2: Solicitud Simple (Firma Simple)

**Actores**: Ciudadano, Orquestador, XLNET, CCP, RdA, SVTs, Dokusi, GILTZA, PPS

**Estados**: Inicio → Cumplimentando → Borrador → Firmada → Enviada/Registrada

**Flujo principal**:

1. **Autenticación e inicio**
   - Ciudadano se autentica mediante XLNET
   - Selecciona procedimiento y acción telemática
   - Sistema recupera configuración desde CCP
   - Sistema obtiene formulario asociado (versión específica)

2. **Identificación de interesados**
   - Ciudadano selecciona tipo: "Para mí" o "Para otro"
   - Si "Para mí": interesado = ciudadano autenticado
   - Si "Para otro": ciudadano proporciona documento de representación firmado por todos
   - Si configurado, sistema consulta RdA para obtener representados disponibles

3. **Prerrellenado automático (si configurado)**
   - Sistema invoca SVTs configurados para prerrellenado
   - Autocompleta campos con datos recuperados
   - Ciudadano puede modificar campos prerrellenados si están habilitados

4. **Cumplimentación del formulario**
   - Ciudadano completa campos requeridos
   - Sistema valida en tiempo real (formato, coherencia)
   - Sistema invoca SVTs de validación si están configurados
   - Ciudadano puede guardar borrador (manual o automático)

5. **Adjuntar documentos**
   - Ciudadano adjunta documentos requeridos
   - Sistema valida formato y tamaño
   - Sistema almacena en Dokusi con metadatos
   - Sistema genera QR para cada documento

6. **Aceptar declaraciones responsables**
   - Sistema muestra declaraciones configuradas en CCP
   - Ciudadano acepta declaraciones obligatorias
   - Sistema registra aceptación con fecha/hora/IP

7. **Revisión y firma**
   - Sistema muestra resumen de toda la información
   - Ciudadano revisa y confirma
   - Sistema invoca componente GILTZA para firma electrónica
   - Ciudadano firma con certificado digital

8. **Envío y registro**
   - Sistema genera PDF justificante
   - Sistema almacena PDF en Dokusi
   - Sistema prepara ejgvDocument (tramitación + negocio)
   - Sistema envía a PPS para registro oficial
   - PPS devuelve número de registro
   - Sistema notifica por email al ciudadano
   - Ciudadano puede descargar justificante

### Proceso 3: Solicitud con Firma Múltiple

**Actores**: Propietario, Interesados firmantes, Orquestador, Sistema de notificaciones

**Estados**: Cumplimentando → Firmada por propietario → Pendientes otras firmas → Rechazada / Completamente firmada → Enviada

**Flujo principal**:

1. **Cumplimentación y primera firma (Propietario)**
   - Propietario cumplimenta el formulario (pasos 1-6 del Proceso 2)
   - Propietario añade interesados firmantes (email obligatorio)
   - Propietario firma la solicitud
   - Sistema bloquea el formulario (no modificable)
   - Propietario NO puede crear otro borrador hasta finalización

2. **Notificación a interesados**
   - Sistema envía email a cada interesado firmante
   - Email contiene enlace de acceso a la solicitud

3. **Firma de cada interesado**
   - Interesado accede mediante enlace (con autenticación)
   - Interesado revisa información (solo lectura)
   - Interesado puede:
     - **Firmar**: Sistema registra firma con fecha/hora
     - **Rechazar**: Proporciona motivo obligatorio

4. **Gestión de rechazo**
   - Si algún interesado rechaza:
     - Sistema desbloquea el formulario
     - Propietario puede modificar y reiniciar proceso
     - Sistema notifica a propietario del rechazo con motivo

5. **Finalización con todas las firmas**
   - Cuando último interesado firma:
     - Sistema registra automáticamente en PPS
     - Sistema genera PDF y lo almacena en Dokusi
     - Sistema notifica por email a TODOS los interesados
     - Solicitud pasa a estado Enviada/Registrada

### Proceso 4: Gestión de Borradores

**Actores**: Ciudadano, Orquestador, Toolkit

**Flujo principal**:

1. **Guardado de borrador**
   - Guardado automático periódico durante cumplimentación
   - Guardado manual cuando ciudadano lo solicita
   - Sistema almacena estado completo (datos + documentos parciales)
   - Solo se mantiene el borrador más reciente por solicitud

2. **Recuperación de borrador**
   - Ciudadano accede a "Mis borradores"
   - Sistema muestra lista filtrada por tipo:
     - Para mí
     - Como representante
     - Como autorizado
   - Ciudadano selecciona borrador
   - Sistema recupera estado completo y permite continuar

3. **Eliminación de borrador**
   - Al enviar solicitud, borrador se elimina automáticamente
   - Ciudadano puede eliminar borrador manualmente

### Proceso 5: Consulta de Solicitudes Enviadas

**Actores**: Ciudadano, Orquestador

**Flujo principal**:

1. Ciudadano accede a "Mis solicitudes"
2. Sistema invoca servicio getRequestInformation
3. Sistema devuelve lista de solicitudes enviadas desde Toolkit Berria
4. Ciudadano puede consultar detalle de cada solicitud (ejgvDocument completo)

**Restricciones**:
- Solo solicitudes enviadas desde Toolkit Berria
- NO incluye solicitudes de antiguo Toolkit o envíos directos a PPS

**Gestión de errores (todos los procesos)**:
- Reintentos automáticos (hasta 3) en integraciones externas
- Logs detallados de errores con timestamp, usuario, acción
- Mensajes de error claros al usuario
- Información de contacto con soporte si error persiste

## 6. Entidades y datos principales

### Formulario (EraiKIT)
- **Campos**: ID oficial (F-OOOO-NNNNNNNNN-V99), nombre, grupo funcional, versión, release, estado (Borrador/Publicado), fecha creación, fecha publicación, autor
- **Componentes**: Lista de componentes del formulario con su configuración
- **SVTs asociados**: Referencias a SVTs utilizados
- **Reglas**: 
  - Un formulario publicado NO puede modificarse
  - Para cambios menores: crear nueva release
  - Para cambios mayores: crear nueva versión
  - ID debe ser único
  - Todos los SVTs asociados deben estar en estado "Publicado" para poder publicar el formulario

### SVT (Servicio de Validación de Terceros)
- **Campos**: ID (SVT-OOOO-NNNNNNNNN), nombre, grupo funcional, descripción, endpoint, tipo (SOAP/REST), operación/método HTTP, parámetros de entrada, esquema de retorno, estado (Mock/Publicado), bloque de respuesta (para Mock), fecha creación
- **Esquemas de retorno**: Validación, Valor simple, Lista simple, Clave-Valor, Tabla de datos
- **Reglas**:
  - SVT de grupo PLATEA-Tramitación es usable por todos
  - SVT de otro grupo solo usable por su grupo
  - SVT en uso no puede eliminarse físicamente
  - SVT en uso solo puede modificarse el campo descripción
  - Para cambios estructurales en SVT usado: crear nuevo SVT

### Procedimiento (desde CCP)
- **Campos**: ID procedimiento, código, nombre, descripción, organismo responsable, estado
- **Acciones telemáticas**: Lista de acciones disponibles (solicitud, subsanación, aportación, justificación)
- **Configuración**: Parámetros de firma, multifirma, multiinteresado, prerrellenado, documentos, declaraciones
- **Relaciones**: Asociado a formularios específicos (versión concreta)

### Acción Telemática (desde CCP)
- **Campos**: ID acción, tipo (solicitud/subsanación/aportación/justificación), ID formulario asociado (versión específica)
- **Configuración**: Firma simple/múltiple, multiinteresado S/N, prerrellenado S/N, lista de documentos requeridos, lista de declaraciones responsables
- **Relaciones**: Pertenece a un procedimiento, asociada a una versión específica de formulario (cualquier release de esa versión se ejecuta automáticamente)

### Solicitud (Orquestador)
- **Campos**: ID solicitud, Folder ID (expediente), ID acción telemática, Instance ID, estado (Borrador/Borrador bloqueado/Pendiente firma/Rechazada/Enviada), fecha creación, fecha última modificación, fecha envío, número de registro
- **ejgvDocument**: 
  - **Datos de tramitación**: Metadatos del proceso
  - **Datos de negocio**: Información cumplimentada en el formulario
- **Documentos adjuntos**: Referencias a documentos en Dokusi
- **Relaciones**: Tiene uno o más interesados, puede tener documentos, puede tener declaraciones aceptadas

### Interesado
- **Campos**: Tipo de persona (1:DNI, 2:CIF, 3:NIE, 4:Pasaporte, 5:Otros, 6:NIE), número identificación, nombre, apellidos (si persona física), razón social (si persona jurídica), email (obligatorio), teléfono (opcional), indicador de firma (S:puede firmar / N:no puede firmar / F:ha firmado), rol (Solicitante/Representado/Representante/Autorizado)
- **Reglas**: 
  - Email obligatorio para todos los interesados firmantes
  - Tipo persona según estándar: 1:DNI, 2:CIF, 3:NIE, 4:Pasaporte, 5:Otros, 6:NIE
  - En firma múltiple, todos deben tener email válido

### Borrador (Orquestador)
- **Campos**: ID borrador, ID usuario propietario, tipo (Para mí/Como representante/Como autorizado), fecha última modificación, datos parciales (JSON), documentos parciales (referencias), estado del formulario
- **Reglas**: 
  - Solo se mantiene el borrador más reciente por usuario y acción telemática
  - Borrador se bloquea durante proceso de firma múltiple
  - Borrador se elimina automáticamente al enviar la solicitud

### Documento
- **Campos**: ID documento en Dokusi, tipo de documento (según configuración CCP), nombre archivo, tamaño, formato, fecha de carga, metadatos, código QR, obligatorio (sí/no)
- **Formatos permitidos**: PDF, DOC, DOCX, JPG, PNG (según configuración CCP por tipo de documento)
- **Reglas**: 
  - Tamaño máximo configurable (típicamente 10MB)
  - Puede permitir múltiples archivos por tipo de documento
  - Sistema genera QR para cada documento almacenado

### Declaración Responsable
- **Campos**: ID declaración, texto completo, tipo (obligatoria/opcional), fecha aceptación, hora aceptación, IP origen, ID usuario
- **Reglas**: Las obligatorias deben estar aceptadas para poder firmar/enviar la solicitud
- **Auditoría**: Registro inmutable de fecha/hora/IP de cada aceptación

### Justificante
- **Campos**: ID justificante, número de registro, fecha/hora generación, ruta PDF en Dokusi, ID solicitud, ID procedimiento, ID acción telemática
- **Contenido del PDF**: Encabezado con logo Gobierno Vasco, número de registro, datos del procedimiento, interesados, datos cumplimentados, documentos adjuntados, declaraciones aceptadas, fecha/hora de presentación, pie de página con validez

### Representado (desde RdA)
- **Campos**: DNI/CIF del representado, nombre/razón social, tipo de apoderamiento, vigencia, DNI/CIF del representante
- **Origen**: Registro de Apoderamientos (RdA)
- **Uso**: Para solicitudes como representante con apoderamiento RdA

### Empresa Autorizadora (desde RdA)
- **Campos**: CIF de la empresa, razón social, lista de autorizados (DNI, nombre, apellidos), vigencia autorización
- **Origen**: Registro de Apoderamientos (RdA)
- **Uso**: Para solicitudes como autorizado de empresa

### Grupo Funcional (EraiKIT)
- **Campos**: Código grupo, nombre, descripción, departamento asociado
- **Tipos**:
  - PLATEA-Tramitación: Accesible por todos
  - Grupos departamentales: Solo accesibles por su departamento
- **Uso**: Control de permisos sobre formularios y SVTs

### Catálogos / Maestras
- **Tipos de documento** (desde CCP): Código, denominación, formatos permitidos, tamaño máximo, obligatorio/opcional
- **Organismos**: Código, nombre, contacto
- **Tipos de persona**: 1:DNI, 2:CIF, 3:NIE, 4:Pasaporte, 5:Otros, 6:NIE

## 6.1 Aspectos funcionales específicos aclarados

### 6.1.1 Autorizaciones (EPIC-006) - ACTUALIZADO 11/02/2026

El sistema gestiona **3 tipos de autorizaciones** para consulta de datos de ciudadanos por la Administración:

1. **Por Ley (mandatorio)**:
   - El ciudadano NO puede oponerse
   - La administración está legalmente autorizada a consultar los datos por mandato legal
   - **NO se muestra en la pantalla** ya que el ciudadano no tiene opción de intervención
   - **SÍ se incluye automáticamente en la solicitud** sin requerir interacción del usuario
   
2. **Salvo oposición (bajo autorización expresa)**:
   - Autorizaciones cuya consulta está autorizada por defecto
   - El ciudadano puede oponerse **selectivamente** a cada autorización
   - Si no se opone, la administración puede consultar
   - Si se opone, debe aportar documentación
   
3. **Únicamente si consiente (bajo consentimiento)**:
   - Autorizaciones que requieren consentimiento explícito del ciudadano
   - El ciudadano debe autorizar **selectivamente** cada autorización
   - Solo si marca explícitamente, la administración puede consultar
   - Si no autoriza, debe aportar documentación

**Configuración**: Se definen en el CCP (Catálogo de Configuración de Procedimientos) indicando tipo de autorización, descripción, datos que se consultarán y organismo cedente.

**Presentación en pantalla (Paso 3 - Autorizaciones)**:

La pantalla incluye tres niveles de controles interrelacionados:

1. **Pregunta global inicial** (obligatoria):
   - "¿Autorizas a la Administración a consultar tus datos?" 
   - Radiobutton con opciones: Sí / No
   - Habilita los bloques de datos y establece selección inicial

2. **Bloque "Datos salvo oposición"** (deshabilitado inicialmente):
   - Switch general que afecta a todas las autorizaciones del bloque
   - Checkbox individual por cada autorización
   - **Textarea para motivo de oposición** (obligatorio si hay oposición a alguna autorización)
   - **Comportamiento**: Checkbox marcado = SE OPONE (debe aportar documento)
   - **Comportamiento**: Checkbox desmarcado = NO se opone (autoriza consulta)

3. **Bloque "Datos únicamente si consiente"** (deshabilitado inicialmente):
   - Switch general que afecta a todas las autorizaciones del bloque
   - Checkbox individual por cada autorización
   - **Comportamiento**: Checkbox marcado = AUTORIZA (puede consultar)
   - **Comportamiento**: Checkbox desmarcado = NO autoriza (debe aportar documento)

**Lógica de interacción**:
- Respuesta **SÍ** (global) → Desmarca todos en "salvo oposición" + Marca todos en "únicamente si consiente"
- Respuesta **NO** (global) → Marca todos en "salvo oposición" + Desmarca todos en "únicamente si consiente" + Muestra textarea de motivo
- Switches generales pueden marcar/desmarcar todos los checkboxes de su bloque
- Checkboxes individuales tienen prioridad y pueden modificarse independientemente
- **Textarea de motivo**: Aparece cuando hay al menos una oposición marcada (obligatorio)
- La sincronización entre controles es automática y bidireccional

**Validación**: 
- Es obligatorio responder la pregunta global para continuar
- Si hay oposición marcada (bloque "salvo oposición"), es obligatorio completar el textarea de motivo
- El ciudadano puede decidir no autorizar ninguna consulta si lo desea (tendrá que aportar todos los documentos)

**Inclusión en la solicitud**:
- Las autorizaciones **"por Ley"** se incluyen automáticamente en la solicitud sin interacción del usuario
- Las autorizaciones **"salvo oposición"** y **"únicamente si consiente"** se incluyen según las decisiones del ciudadano
- Si hay oposiciones, se incluye el **motivo de la oposición** especificado por el ciudadano

**Impacto en documentos**: Si el ciudadano se opone o no concede alguna autorización, los documentos relacionados aparecerán como **obligatorios en el Paso 4 (Documentos)**. Las autorizaciones son en realidad documentos configurados en el CCP.

### 6.1.2 Presencial Ciudadanía (EPIC-007)

**Modalidad especial de presentación** donde el ciudadano completa una solicitud sin autenticación para luego presentarla presencialmente en oficinas.

**Características principales**:
- **Tipo de presentación**: tipoPresentación=19 (identificador específico)
- **Sin autenticación**: El ciudadano NO se autentica electrónicamente
- **Sin firma electrónica**: No se solicita firma digital
- **Identificación de interesados**: Introducción **manual mediante formulario**
- **Sin consulta a registros**: NO se consulta Registro de Interesados (RI) ni Registro de Apoderamientos (RdA)
- **Sin borradores**: NO se pueden guardar borradores recuperables
- **Sin plantillas**: NO se pueden cargar ni guardar plantillas de solicitudes
- **Interfaz simplificada**: No se muestran enlaces a borradores, plantillas ni funcionalidades relacionadas
- **Configuración**: Habilitación por procedimiento en el CCP
- **Terminología**: Se denomina "solicitud presencial" (NO "presolicitud")

**Acceso y selección de tipo de tramitación**:
1. Ciudadano accede mediante URL con código procedimiento + idAcciónTelemática=19
2. Sistema omite proceso de autenticación
3. Sistema presenta pantalla: "¿Cómo desea proceder con la tramitación?"
   - Opción: "Para mí" (tramita para sí mismo)
   - Opción: "Para otros" (tramita en representación)
4. Ciudadano selecciona tipo de tramitación

**Flujo de rellenado**:
1. Ciudadano introduce manualmente datos de identificación (solicitante y representados si aplica)
2. Sistema NO consulta RI ni RdA durante la introducción de datos
3. Ciudadano cumplimenta formulario completo (pasos 1-5)
4. Ciudadano aporta documentos que se almacenan en **Dokusi**
5. Sistema NO solicita firma
6. Sistema guarda solicitud presencial con código único
7. Sistema genera PDF con:
   - Código QR integrado en el documento (servicio de Dokusi)
   - Datos de identificación de la solicitud presencial
   - Resumen de datos cumplimentados

**Opciones de descarga**:
- PDF completo con QR integrado
- Imagen PNG o JPEG del QR únicamente (para facilitar envío por email/WhatsApp)

**Instrucciones al ciudadano** (4 pasos en pantalla de finalización):
1. Imprimir el PDF generado (o tener el QR en móvil)
2. Acudir a una oficina de registro presencial
3. Identificarse físicamente ante funcionario
4. Presentar el documento con QR para registro oficial

**Almacenamiento**: Documentos aportados se guardan en **Dokusi** (gestor documental corporativo).

### 6.1.3 Subsanación - Proceso del Ciudadano (EPIC-008)

**Acción telemática especial** donde el ciudadano corrige datos o documentos marcados por el tramitador.

**Acceso**:
- Desde **Mi Carpeta** (aplicación ciudadano del Gobierno Vasco)
- Vía **apilamiento remoto**: XML con rutas PIF de documentos de requerimiento
- El ciudadano ve notificación de requerimiento con enlace a Toolkit
- **Plazo de subsanación**: Gestionado por Mi Carpeta (elimina enlace si caduca)
- Puede subsanar: interesado, representante o autorizado

**Comportamiento del formulario**:

**Paso 2 - Datos Específicos**:
- Se precargan con los datos de la **solicitud original** exactamente
- Estructura **idéntica** a la solicitud original
- Todas las validaciones del paso 2 se aplican igual
- Campos están habilitados/deshabilitados según configuración "marcado para subsanar"
- Ciudadano solo puede modificar campos marcados como "a subsanar"
- **Datos de interesados y notificación**: NO modificables

**Paso 3 - Autorizaciones**:
- Se carga según configuración del **CCP para subsanación**
- Se presenta **vacío** (NO se precargan autorizaciones de solicitud original)
- Ciudadano completa según configuración

**Paso 4 - Documentos**:
- Se carga según configuración del **CCP para subsanación**
- Se presenta **vacío** (NO se precargan documentos de solicitud original)
- Ciudadano consulta documento de requerimiento adjunto a notificación
- Ciudadano aporta documentos solicitados en requerimiento

**Paso 5 - Declaraciones**:
- Se carga según configuración del **CCP para subsanación**
- Se presenta **vacío** (NO se precargan declaraciones de solicitud original)
- Ciudadano acepta declaraciones configuradas
- **NO tienen texto variable** (solo pueden estar condicionadas a mostrarse o no)

**Activación condicional**:
- Solo se activan campos dependientes si el campo condicionante está **marcado como "a subsanar"**
- Resto de campos condicionados NO se activan aunque cambien valores

**Gestión de borradores**:
- Sistema permite guardar borrador de subsanación
- **UN SOLO borrador por expediente/usuario**
- Si existe borrador previo, sistema lo recupera automáticamente
- Si no existe, sistema carga borrador inicial del tramitador

**Validaciones**:
- Se realizan en **cada paso individual** según configuración de obligatoriedad
- NO hay validación global al final
- Sistema no permite avanzar si no se cumplen validaciones del paso actual

**Firma y envío**:
- Firma electrónica igual que solicitud normal
- Sistema registra subsanación en sistema tramitador
- Genera justificante de subsanación
- **Envía justificante por email** al ciudadano
- Actualiza estado del expediente

**Información del requerimiento**:
- **Motivo de subsanación**: En documento adjunto a notificación (NO en Toolkit)
- **Plazo**: Indicado en notificación, gestionado por Mi Carpeta
- **Elementos a subsanar**: Detallados en documento de requerimiento

**Restricciones**:
- **Un único requerimiento por expediente** en cada momento
- No se modifica estructura de interesados de solicitud original
- No se muestra histórico de requerimientos (responsabilidad de Mi Carpeta)

## 7. Integraciones y sistemas externos

### XLNET (Sistema de Autenticación)
- **Propósito**: Autenticación de personas usuarias (ciudadanos)
- **Protocolo**: Integración corporativa del Gobierno Vasco
- **Datos intercambiados**: 
  - **Salida**: Identidad del usuario autenticado (NIF/CIF, nombre, apellidos/razón social, email)
- **Eventos**: Inicio de sesión, cierre de sesión
- **Nota**: Gestionado por la aplicación base, fuera del alcance de Toolkit Berria

### CCP (Catálogo de Configuración de Procedimientos)
- **Propósito**: Sistema maestro de configuración de procedimientos administrativos. Proporciona información de procedimientos, acciones telemáticas, formularios asociados, configuración de firma, documentos requeridos, declaraciones responsables. Coordina traspaso de formularios entre entornos.
- **Protocolo**: REST / SOAP
- **Datos intercambiados**: 
  - **Entrada desde Orquestador**: ID procedimiento, ID acción telemática
  - **Salida hacia Orquestador**: Configuración completa (ID formulario, versión, configuración de firma, multifirma, multiinteresado, prerrellenado, lista de documentos, lista de declaraciones, configuración de SVTs)
  - **Entrada desde EraiKIT**: Consulta de formularios publicados
  - **Salida hacia EraiKIT**: Información de formularios disponibles
- **Eventos**: 
  - Consulta de configuración al iniciar solicitud
  - Traspaso de formularios entre entornos vía PIF
- **Funciones**:
  - Coordina traspaso de formularios mediante proceso PIF
  - Si versión/release ya existe en destino, NO se actualiza
  - Si formulario compartido por varios procedimientos, traspasar todos

### RdA (Registro de Apoderamientos)
- **Propósito**: Gestión de representaciones y autorizaciones. Proporciona lista de representados de un ciudadano y empresas autorizadoras con sus autorizados.
- **Protocolo**: REST / SOAP
- **Datos intercambiados**: 
  - **Entrada**: DNI/CIF del ciudadano autenticado
  - **Salida**: 
    - Lista de representados (DNI/CIF, nombre/razón social, tipo de apoderamiento, vigencia)
    - Lista de empresas autorizadoras (CIF, razón social, lista de autorizados, vigencia)
- **Eventos**: Consulta al seleccionar "Como representante" o "Como autorizado"
- **Restricciones**: NO se puede usar apoderamientos RdA para solicitudes "Para otro" (requiere representación específica por solicitud con documento firmado)

### Dokusi (Repositorio de Documentos de la Administración)
- **Propósito**: Almacenamiento centralizado y seguro de documentos electrónicos. Guardado de documentos adjuntos y PDF justificantes.
- **Protocolo**: REST y SOAP
- **Datos intercambiados**: 
  - **Entrada hacia Dokusi**: Documentos adjuntados (binario), PDF justificante generado, metadatos (ID solicitud, tipo documento, fecha, usuario, ID procedimiento)
  - **Salida desde Dokusi**: Referencia/ID del documento almacenado, código QR, confirmación de almacenamiento
- **Eventos**: 
  - Subida de documento durante cumplimentación
  - Almacenamiento de PDF justificante tras envío
  - Generación de QR para cada documento
- **Funcionalidades**:
  - Generación de código QR para cada documento
  - Definición de metadatos personalizados
- **Gestión de errores**: Reintentos automáticos hasta 3 veces, cola de procesamiento diferido si falla

### GILTZA (Sistema de Autenticación y Firma Electrónica)
- **Propósito**: Componente de firma electrónica de Izenpe. Permite firma simple y múltiple de solicitudes.
- **Protocolo**: Componente integrado
- **Tipos de componente**: 
  - GILTZA Ciudadano: Para personas físicas
  - GILTZA Profesional: Para representantes/autorizados de empresas
- **Datos intercambiados**: 
  - **Entrada**: Datos a firmar (resumen de solicitud)
  - **Salida**: Firma electrónica, certificado digital, fecha/hora de firma
- **Eventos**: 
  - Firma simple: Al confirmar envío
  - Firma múltiple: Primera firma del propietario, firmas sucesivas de interesados

### PPS (Proceso de Presentación de Solicitudes / Tramitagune)
- **Propósito**: Sistema de gestión de expedientes. Registro oficial de solicitudes para tramitación posterior.
- **Protocolo**: REST / SOAP
- **Datos intercambiados**: 
  - **Entrada hacia PPS**: ejgvDocument con datos de tramitación (metadatos) y datos de negocio (información del formulario), Folder ID, ID acción telemática, Instance ID, lista de interesados, referencias a documentos en Dokusi, referencia a PDF justificante, fecha/hora envío
  - **Salida desde PPS**: Confirmación de recepción (código 200), número de registro único
- **Eventos**: Envío de solicitud tras firma (simple o última firma en múltiple)
- **Gestión de errores**: Reintentos automáticos hasta 3 veces, registro en cola de reintento si falla persistentemente

### Toolkit (Servicio de Guardado)
- **Propósito**: Servicio interno de guardado de solicitudes y borradores
- **Protocolo**: REST
- **Datos intercambiados**: 
  - **Entrada**: Datos de solicitud/borrador (JSON), documentos parciales, estado, usuario propietario
  - **Salida**: Confirmación de guardado, ID borrador
- **Eventos**: 
  - Guardado automático periódico
  - Guardado manual por el usuario
  - Recuperación de borrador

### Toolkit-Plantillas (Servicio de Plantillas)
- **Propósito**: Servicio interno de guardado de plantillas reutilizables
- **Protocolo**: REST
- **Datos intercambiados**: 
  - **Entrada**: Datos de plantilla (JSON), nombre, descripción, usuario propietario
  - **Salida**: Confirmación de guardado, ID plantilla, lista de plantillas del usuario
- **Eventos**: 
  - Guardado de plantilla
  - Recuperación de plantilla

### SVTs (Servicios de Validación de Terceros)
- **Propósito**: Microservicios/APIs departamentales para validar información y recuperar datos para prerrellenado automático
- **Protocolo**: SOAP / REST (según configuración de cada SVT)
- **Tipos de servicios**: Departamentales específicos según necesidades de cada procedimiento
- **Esquemas de retorno**: 
  - **Validación**: Retorna true/false con mensaje de error si procede
  - **Valor simple**: Retorna un único valor
  - **Lista simple**: Retorna array de valores
  - **Clave-Valor**: Retorna pares clave-valor
  - **Tabla de datos**: Retorna estructura tabular compleja
- **Datos intercambiados**: 
  - **Entrada**: Parámetros definidos en configuración del SVT (valores de campos del formulario)
  - **Salida**: Según esquema de retorno configurado
- **Eventos**: 
  - Prerrellenado automático al cargar formulario
  - Validación en tiempo real al cumplimentar campos
- **Estados**: Mock (simulado para pruebas) / Publicado (servicio real)

### OSB (Oracle Service Bus)
- **Propósito**: Plataforma de exposición de SVTs
- **Protocolo**: Bus de servicios
- **Función**: Intermediario para servicios departamentales

### PIF (Plataforma de Integración de Ficheros)
- **Propósito**: Traspaso de configuración de formularios entre entornos (desarrollo → pruebas → producción)
- **Protocolo**: Apilamiento remoto
- **Proceso**: 
  - CCP coordina el traspaso
  - Se traspasa versión + releases + SVTs asociados
  - Si versión/release ya existe en destino, NO se actualiza
  - Si formulario compartido por varios procedimientos, traspasar todos

### Mi Carpeta
- **Propósito**: Aplicación ciudadano del Gobierno Vasco para consultar solicitudes, borradores, plantillas y notificaciones
- **Protocolo**: Integración mediante apilamiento remoto (XML)
- **Funcionalidades**:
  - Consulta de solicitudes presentadas
  - Acceso a notificaciones de requerimientos
  - Gestión de plazos de subsanación
  - Visualización de documentos de requerimiento
- **Apilamiento remoto**: XML que incluye rutas PIF de documentos sin almacenarlos directamente en Mi Carpeta
- **Datos intercambiados**:
  - **Entrada hacia Toolkit**: Identificador de expediente, usuario autenticado, tipo de acción (subsanación)
  - **Salida desde Toolkit**: Estado de subsanación, confirmación de envío
- **Gestión de plazos**: 
  - Muestra plazo de subsanación al ciudadano
  - Elimina enlace de acceso si plazo caduca
  - NO gestiona histórico de requerimientos (responsabilidad de Mi Carpeta)
- **Restricciones**: Solo un requerimiento activo por expediente

### Sistema de Notificaciones (Email)
- **Propósito**: Envío de notificaciones por correo electrónico
- **Protocolo**: SMTP / API REST de sistema de email corporativo
- **Datos intercambiados**: 
  - **Entrada**: Email destinatario, asunto, cuerpo del mensaje, PDF justificante (opcional)
- **Eventos**: 
  - Notificación tras envío de solicitud
  - Notificación a interesados en firma múltiple
  - Notificación de firma recibida
  - Notificación de rechazo de firma
  - Notificación de registro final tras todas las firmas

### RI (Registro de Interesados)
- **Propósito**: Sistema de registro de ciudadanos (personas físicas y jurídicas)
- **Nota**: Gestionado externamente, fuera del alcance de Toolkit Berria

## 8. Reglas de negocio globales

### Gestión de Formularios (EraiKIT)
- **RB-01**: Un formulario en estado "Publicado" NO puede modificarse (inmutabilidad)
- **RB-02**: Para cambios menores (textos, reorganización visual): crear nueva release (incremento de número release)
- **RB-03**: Para cambios mayores (componentes, validaciones, SVTs): crear nueva versión (incremento de número versión)
- **RB-04**: La relación Procedimiento-Acción Telemática se hace con una versión específica de formulario
- **RB-05**: Cualquier release de esa versión se ejecuta automáticamente (sin necesidad de reconfigurar en CCP)
- **RB-06**: El ID del formulario debe ser único: F-OOOO-NNNNNNNNN-V99 (Grupo funcional-Nombre-Versión)

### Gestión de SVTs
- **RB-07**: SVT de grupo "PLATEA-Tramitación" es usable por cualquier formulario
- **RB-08**: SVT de otro grupo funcional solo es usable por formularios del mismo grupo
- **RB-09**: SVT en estado "Mock" impide la publicación de formularios que lo utilizan
- **RB-10**: SVT en uso NO puede eliminarse físicamente del catálogo
- **RB-11**: SVT en uso solo puede modificarse el campo "descripción"
- **RB-12**: Para cambios estructurales en SVT usado: crear nuevo SVT con nuevo ID

### Traspaso entre Entornos
- **RB-13**: EraiKIT solo existe en entorno de desarrollo
- **RB-14**: CCP coordina el traspaso a entornos de pruebas y producción mediante proceso PIF
- **RB-15**: Se traspasan: versión + todas las releases + SVTs asociados
- **RB-16**: Si versión/release ya existe en destino, NO se actualiza (no se sobrescribe)
- **RB-17**: Si formulario es compartido por varios procedimientos, traspasar todos los procedimientos que lo usan
- **RB-18**: Para traspasar solo releases nuevas, basta con traspasar un procedimiento que use el formulario

### Firma Múltiple
- **RB-19**: El propietario de la solicitud debe firmar primero
- **RB-20**: Al firmar el propietario, el formulario se bloquea (no modificable)
- **RB-21**: El propietario NO puede crear otro borrador mientras tenga una solicitud en proceso de firma múltiple
- **RB-22**: Cualquier interesado firmante puede rechazar la solicitud proporcionando motivo obligatorio
- **RB-23**: Si hay rechazo, el formulario vuelve a estado modificable para el propietario
- **RB-24**: Cuando el último interesado firma, el sistema registra automáticamente en PPS y envía notificaciones a TODOS
- **RB-25**: Email es obligatorio para todos los interesados firmantes (para notificaciones)

### Representación
- **RB-26**: Solicitud "Para mí": solicitante es el ciudadano autenticado
- **RB-27**: Solicitud "Para otro": requiere representación específica por solicitud con documento acreditativo firmado por todos los interesados
- **RB-28**: NO se puede usar apoderamientos RdA para solicitudes "Para otro" (solo para "Como representante")
- **RB-29**: Los representados y empresas autorizadoras se obtienen automáticamente de RdA según el ciudadano autenticado
- **RB-30**: El sistema registra siempre quién realiza cada acción (interesado, representante o autorizado)

### Solicitudes y Borradores
- **RB-31**: Solo se mantiene el borrador más reciente por usuario y acción telemática
- **RB-32**: Al enviar una solicitud, el borrador se elimina automáticamente
- **RB-33**: Una vez enviada la solicitud (tras firma), NO se permite volver atrás ni realizar modificaciones (inmutabilidad)
- **RB-34**: Guardado automático de borradores se realiza periódicamente durante cumplimentación
- **RB-35**: El servicio getRequestInformation solo devuelve solicitudes enviadas desde Toolkit Berria (NO incluye antiguo Toolkit ni envíos directos a PPS)

### Documentos
- **RB-36**: Todos los documentos marcados como obligatorios deben ser adjuntados para poder firmar/enviar
- **RB-37**: Formatos de documento permitidos según configuración en CCP por tipo de documento (típicamente: PDF, DOC, DOCX, JPG, PNG)
- **RB-38**: Tamaño máximo por documento configurable en CCP (valor típico: 10MB)
- **RB-39**: El sistema genera código QR para cada documento almacenado en Dokusi

### Validaciones y Declaraciones
- **RB-40**: Todas las declaraciones responsables marcadas como obligatorias deben ser aceptadas para poder firmar/enviar
- **RB-41**: Todas las validaciones de campos obligatorios deben cumplirse para poder avanzar
- **RB-42**: Las validaciones mediante SVTs se ejecutan en tiempo real durante la cumplimentación

### Auditoría y Trazabilidad
- **RB-43**: Todas las acciones del usuario deben quedar registradas en auditoría (fecha/hora, IP, acción, ID usuario, ID solicitud)
- **RB-44**: Los registros de auditoría son inmutables (no pueden modificarse ni eliminarse)
- **RB-45**: La aceptación de declaraciones responsables se registra con fecha/hora/IP de forma inmutable

### Tipos de Persona
- **RB-46**: Tipo de persona según estándar: 1:DNI, 2:CIF, 3:NIE, 4:Pasaporte, 5:Otros, 6:NIE
- **RB-47**: Este tipo se utiliza en ejgvDocument enviado a PPS para identificar correctamente a los interesados

### Número de Registro
- **RB-48**: El número de registro de la solicitud debe ser único e irrepetible
- **RB-49**: El número de registro es generado por PPS al recibir la solicitud

## 9. Requisitos no funcionales (NFR)

### Seguridad
- **Autenticación**: Mediante sistema corporativo del Gobierno Vasco (XLNET/GILTZA)
- **Autorización**: 
  - El ciudadano solo puede acceder a sus propias solicitudes
  - Los representantes solo a las de sus representados (según RdA)
  - Los autorizados solo a las de sus empresas autorizadoras (según RdA)
  - Configuradores solo acceden a formularios y SVTs de su grupo funcional (excepto PLATEA-Tramitación que es público)
- **Cifrado**: Comunicaciones HTTPS/TLS obligatorias, datos sensibles cifrados en tránsito y reposo
- **Cumplimiento OWASP**: Protección contra inyección SQL, XSS, CSRF, etc.
- **Validación de entrada**: Todas las entradas del usuario deben ser validadas y sanitizadas
- **Firma electrónica**: Mediante componente GILTZA (Izenpe) con certificados digitales válidos
- **Protección ante bots**: Mecanismos de defensa ante ataques automatizados (pendiente de definir específicamente)
- **Protección de APIs**: Autenticación y autorización en todos los endpoints

### Auditoría y trazabilidad
- **Qué se registra**: 
  - EraiKIT: Creación, modificación y publicación de formularios y SVTs, usuario, fecha/hora
  - Orquestador: Todas las acciones del usuario (inicio sesión, acceso a solicitud, edición de campos, carga de documentos, aceptación de declaraciones, guardado de borrador, firma, envío), fecha/hora, IP origen, ID usuario, ID solicitud, ID procedimiento, acción realizada
  - Firma múltiple: Cada firma y rechazo con motivo, fecha/hora, IP, usuario firmante
- **Dónde se registra**: Sistema de logs centralizado, base de datos de auditoría
- **Inmutabilidad**: Los registros de auditoría no pueden ser modificados ni eliminados
- **Retención**: Según normativa de conservación de documentos del Gobierno Vasco
- **Consulta**: Acceso a logs de auditoría para administradores y auditores autorizados

### Rendimiento
- **Tiempos de respuesta**: 
  - Autenticación: < 2 segundos
  - Carga inicial del formulario: < 3 segundos
  - Validaciones en tiempo real: < 500ms
  - Invocación a SVTs (prerrellenado/validación): < 2 segundos
  - Carga de documento (hasta 10MB): < 10 segundos
  - Generación de PDF y envío a PPS: < 15 segundos
  - Guardado de borrador: < 1 segundo
- **Volumen esperado**: 
  - Usuarios concurrentes: hasta 1.000 en horario pico
  - Formularios en catálogo: estimación de varios cientos
  - SVTs en catálogo: estimación de decenas por grupo funcional
  - Picos de carga en fechas límite de plazos: escalado automático
- **Disponibilidad del servicio**: 
  - Objetivo: 99.5% anual (excluidas ventanas de mantenimiento programado)
  - EraiKIT: Solo en desarrollo (disponibilidad durante horario laboral)
  - Orquestador: 24/7 en producción
- **Pruebas de estrés**: Obligatorias con herramientas EJIE antes de paso a producción

### Accesibilidad
- **Estándar**: WCAG 2.1 nivel AA obligatorio
- **Idiomas**: Euskera y castellano (multiidioma obligatorio)
- **Dispositivos**: 
  - Responsive design obligatorio
  - Compatible con dispositivos móviles, tablets y ordenadores
  - Optimización para diferentes tamaños de pantalla
- **Navegadores soportados**: 
  - Chrome (versiones actualizadas)
  - Firefox (versiones actualizadas)
  - Safari (versiones actualizadas)
  - Edge (versiones actualizadas)
- **Ayudas técnicas**: 
  - Compatible con lectores de pantalla (JAWS, NVDA)
  - Navegación por teclado completa
  - Alto contraste soportado
- **Ayudas contextuales**: 
  - EraiKIT: Consejos y guías interactivas para configuradores
  - Orquestador: Ayudas en cada paso del proceso para ciudadanos

### Disponibilidad
- **Ventanas de servicio**: 
  - EraiKIT: Horario laboral en entorno de desarrollo
  - Orquestador: 24/7 excepto ventanas de mantenimiento programado (notificadas previamente)
- **RTO (Recovery Time Objective)**: < 4 horas para servicios críticos
- **RPO (Recovery Point Objective)**: < 1 hora
- **Backup**: 
  - Diario automático
  - Retención según política corporativa
  - Pruebas de recuperación periódicas
- **Alta disponibilidad**: Arquitectura redundante en producción

### Cumplimiento
- **RGPD**: Cumplimiento completo de Reglamento General de Protección de Datos personales
  - Consentimiento explícito cuando proceda
  - Derecho al olvido
  - Portabilidad de datos
  - Minimización de datos
- **ENS**: Esquema Nacional de Seguridad
  - Nivel medio/alto según clasificación de datos
  - Evaluación de conformidad periódica
- **Normativas sectoriales**: 
  - Ley 39/2015 de Procedimiento Administrativo Común
  - Ley 40/2015 de Régimen Jurídico del Sector Público
  - Normativa específica del Gobierno Vasco
- **Conservación de documentos**: Según normativa aplicable del Gobierno Vasco y legislación estatal
- **Firma electrónica**: Cumplimiento eIDAS (Reglamento UE 910/2014)

### Usabilidad
- **Facilidad de uso**: Interfaz intuitiva con mínima curva de aprendizaje
- **Consistencia**: Mismo look & feel en todo el sistema
- **Mensajes de error**: Claros, específicos y orientados a la solución
- **Feedback inmediato**: El usuario debe saber siempre qué está pasando (indicadores de carga, confirmaciones)
- **Prevención de errores**: Validaciones en tiempo real, confirmaciones antes de acciones irreversibles

### Escalabilidad
- **Arquitectura**: Microservicios escalables horizontalmente
- **Base de datos**: Optimizada para crecimiento de volumen de datos
- **Catálogos**: Preparados para crecimiento significativo de formularios y SVTs
- **Caché**: Estrategia de caché para configuraciones frecuentemente consultadas (CCP, formularios publicados)

## 10. Restricciones y supuestos de proyecto

### Tecnologías impuestas
- **Arquitectura**: Microservicios con APIs REST/SOAP
- **Frontend**: Framework moderno responsive (React, Angular o Vue.js - según estándar EJIE)
- **Backend**: Java / Spring Boot (estándar EJIE)
- **Base de datos**: PostgreSQL (corporativa)
- **Gestión documental**: Dokusi (sistema corporativo del Gobierno Vasco)
- **Autenticación**: XLNET (sistema corporativo del Gobierno Vasco)
- **Firma electrónica**: GILTZA / Izenpe (sistema corporativo del Gobierno Vasco)
- **Bus de servicios**: OSB (Oracle Service Bus) para exposición de SVTs
- **Traspaso entre entornos**: PIF (Plataforma de Integración de Ficheros)

### Limitaciones de entorno
- **EraiKIT**: Solo disponible en entorno de desarrollo (no en pruebas ni producción)
- **Traspaso de configuración**: 
  - Coordinado por CCP mediante proceso PIF
  - No hay sincronización automática entre entornos
  - Si versión/release ya existe en destino, no se sobrescribe
- **Integración con sistemas legacy**: Algunos sistemas externos pueden tener limitaciones técnicas o tiempos de respuesta elevados
- **Red corporativa**: Acceso restringido a sistemas internos del Gobierno Vasco
- **Entornos**: Desarrollo, Pruebas, Preproducción, Producción
- **SVTs en estado Mock**: Impiden la publicación de formularios que los usan

### Dependencias con terceros
- **CCP (Catálogo de Configuración de Procedimientos)**: 
  - Configuración correcta de procedimientos y acciones telemáticas
  - Disponibilidad del servicio de consulta
  - Coordinación del proceso PIF para traspasos
- **RdA (Registro de Apoderamientos)**: 
  - Disponibilidad y actualización de datos de apoderamientos
  - Datos correctos de representados y empresas autorizadoras
- **Dokusi**: 
  - Capacidad de almacenamiento suficiente
  - Disponibilidad del servicio
  - Tiempos de respuesta adecuados
- **PPS/Tramitagune**: 
  - Disponibilidad del API de recepción de solicitudes
  - Generación correcta de números de registro únicos
- **XLNET/GILTZA**: 
  - Disponibilidad de servicios de autenticación y firma
  - Certificados digitales válidos
- **SVTs departamentales**: 
  - Desarrollo y mantenimiento por departamentos propietarios
  - Disponibilidad y tiempos de respuesta adecuados
  - Configuración correcta en catálogo de EraiKIT

## 11. Referencias al Glosario

Para consultar la terminología completa del proyecto, ver el archivo [GLOSARIO.md](../GLOSARIO.md) en la raíz del proyecto.

El glosario unificado contiene términos técnicos y de negocio relacionados con el proyecto.
El glosario es un elemento vivo que se tiene que ir enriqueciendo a medida que se va avanzando con el proyecto y la creación de épicas e historias.

## 12. Convenciones de redacción (para historias)
### Formato de IDs
- **Épicas**: EPIC-XXX (ejemplo: EPIC-001, EPIC-002)
- **Historias de Usuario**: US-XXX (ejemplo: US-001, US-002)
- **Preguntas/Supuestos**: EPIC-XXX_questions.md o US-XXX_questions.md
- **Formularios en EraiKIT**: F-OOOO-NNNNNNNNN-V99 (Grupo funcional-Nombre-Versión)
  - Ejemplo: F-0001-FormAyudas-V01
- **SVTs**: SVT-OOOO-NNNNNNNNN (Grupo funcional-Nombre)
  - Ejemplo: SVT-0001-ValidarNIF

### Nomenclatura de estados
- **Épicas**: Planificada, En desarrollo, Completada
- **Historias de Usuario**: Not Started, In Progress, In Review, Done
- **Formularios (EraiKIT)**: Borrador, Publicado
- **SVTs**: Mock, Publicado
- **Solicitudes (Orquestador)**: Borrador, Borrador bloqueado (firma múltiple), Pendiente firma, Rechazada, Enviada/Registrada
- **Proceso de solicitud**: Inicio → Cumplimentando → Borrador → Firmada → Enviada → Registrada

### Criterios de aceptación
- **Formato preferido**: Gherkin (Given/When/Then)
  - **Given** (Dado): Contexto o estado inicial
  - **When** (Cuando): Acción o evento que ocurre
  - **Then** (Entonces): Resultado esperado observable
  - **And**: Para añadir condiciones o resultados adicionales
- **Idioma**: Español
- **Verificabilidad**: Todos los criterios deben ser objetivos, testeables y sin ambigüedad
- **Cobertura**: Al menos un escenario feliz (happy path) y escenarios de error/excepción

### Nomenclatura de componentes técnicos
- **EraiKIT**: Compositor de Formularios (backend de configuración)
- **Orquestador**: Sistema de ejecución (backend + frontend ciudadano)
- **Frontend Ciudadano**: Interfaz web para ciudadanos
- **Frontend EraiKIT**: Interfaz web para configuradores (solo desarrollo)
- **Servicios REST/SOAP**: APIs de integración con sistemas externos
- **Microservicios**: Componentes de backend independientes y escalables

### Convenciones de documentación
- **Lenguaje**: Español profesional, orientado a administración pública/entornos corporativos
- **Términos técnicos**: Usar glosario definido en esta sección 11
- **Siglas**: Definir siempre en la primera aparición, luego usar solo la sigla
- **Ejemplos**:  NO Incluir ejemplos concretos 
- **Referencia a documentos fuente**: Citar sección del documento funcional cuando se derive un requisito de él

---

*Última actualización: 30/01/2026*
*Basado en: Toolkit Berria ASI - Compositor de Formularios v1.4.docx y Toolkit Berria ASI - Orquestador v1.4.docx*
*Actualizado con aclaraciones funcionales de: EPIC-006 (Autorizaciones), EPIC-007 (Presencial Ciudadanía), EPIC-008 (Subsanación)*

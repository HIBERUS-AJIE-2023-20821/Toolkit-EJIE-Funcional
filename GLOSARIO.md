# GLOSARIO DE TÉRMINOS - ToolkitBerria

---

**Fuente:** Documentación Funcional ASI - Compositor de Formularios y Orquestador v1.4  
**Versión:** 2.1  
**Fecha de creación:** 26/01/2026  
**Última actualización:** 30/01/2026  
**Responsable:** Product Owner Assistant

---

## A

### Acción Condicional
Conjunto de acciones asociadas a un componente que pueden estar condicionadas al valor aportado en otro componente o aplicarse sobre el componente sin condición ninguna. Permite realizar acciones como resultado de una validación o de un evento.

### Acción Telemática
Tipo de trámite electrónico (solicitud, subsanación, aportación, justificación) asociado a un procedimiento administrativo. También puede incluir: aceptación, recurso, alegación, desistimiento, renuncia, aplazamiento.

### Alertas
Componente que muestra mensajes de aviso ante finalizaciones exitosas o validaciones de datos incorrectos, incompletos o incongruentes.

### Anónimo
Tipo de procedimiento que permite la presentación de solicitudes sin necesidad de autenticación electrónica del ciudadano. Pueden ser con correo electrónico obligatorio, sin correo electrónico obligatorio o sin datos identificativos.

### Apartado
Índice principal del formulario que mostrará los principales grupos de información a capturar. Componente organizativo de primer nivel.

### API
Application Programming Interface. Interfaz que expone servicios para ser consumidos por terceros.

### ARINbide
Licencia Creative Commons bajo la cual está licenciado el contenido (Reconocimiento-NoComercial-CompartirIgual 3.0).

### Autenticación
Proceso de validación de identidad del usuario mediante certificado electrónico o Giltza.

### Autorización
Documento o consentimiento que la persona solicitante debe expresar para que la Administración pueda consultar datos relacionados con el interesado. Pueden ser "salvo oposición", "únicamente si consiente" o "por Ley".

### Autorizaciones (Paso 3)
Paso del orquestador donde la persona conectada puede marcar su consentimiento o no a la consulta de datos por parte de la Administración.

### Autorizado
Persona que tiene autorización de una entidad en el Registro de Apoderamiento (RdA) para actuar en su nombre.

### Autorizador
Entidad que autoriza a una persona para actuar en su nombre.

### Apilamiento Remoto
Mecanismo de integración entre ToolkitBerria y Mi Carpeta mediante XML que incluye rutas PIF de documentos para que el ciudadano pueda acceder a documentos de requerimiento desde Mi Carpeta sin almacenarlos directamente en ella.

## B

### Backend
Aplicativos que se consumen en la red privada (intranet) del Gobierno Vasco.

### Bloque
Grupos de datos necesarios a nivel visual dentro de una sección (ej: datos de vehículo ligero, datos de vehículo pesado). Permite visualización de componentes organizados.

### Bloque de Repetición
Componente bloque configurado para permitir añadir múltiples instancias del mismo durante la cumplimentación de la solicitud. Los componentes internos no pueden ser referenciados en validaciones condicionales.

### Borrador
Elemento identificativo de una solicitud o acción telemática que no finalizó su tramitación, permitiendo su recuperación y continuación. Se guarda automáticamente con un identificador único de solicitud.

## C

### calendarAge
Función que calcula la edad actual de una persona a partir de su fecha de nacimiento.

### calendarIntervalDays
Función que calcula el intervalo en días naturales entre dos fechas.

### calendarIntervalMonths
Función que calcula el intervalo entre dos fechas medido en periodos de 30 días naturales.

### calendarIntervalYears
Función que calcula el intervalo entre dos fechas medido en periodos de 365 días naturales.

### calendarNow
Función que devuelve la fecha y hora actual según el reloj y zona horaria del ordenador donde se ejecuta.

### Cambiar Texto
Acción que permite cambiar el valor de la etiqueta de un componente cuando se cumple una condición.

### CAPV
Comunidad Autónoma del País Vasco.

### Cargar Grupo Repetición
Acción que recupera datos desde un SVT para cargar cada componente de un grupo de repetición, tabla o bloque/módulo de repetición.

### Cargar Valores Fijos
Acción que aplica un valor preestablecido a un componente en base al cumplimiento de una condición.

### Catálogo de Formularios
Aplicativo que registra los formularios y ofrece servicios consumidos tanto por el Compositor como por el CCP. Se mantiene desde el Compositor en desarrollo y tiene réplicas en PRE y PRO.

### Catálogo de SVT's
Aplicativo que contiene el registro de servicios de terceros requeridos por los formularios. Se mantiene desde el Compositor en desarrollo y tiene réplicas en PRE y PRO.

### CCP
Catálogo de Configuración de Procedimientos. Sistema maestro que mantiene la configuración de todos los procedimientos administrativos y acciones telemáticas del Gobierno Vasco (campos, documentos, validaciones, declaraciones, asociación con formularios). Coordina el traspaso de formularios entre entornos mediante proceso PIF.

### Centro
División de una entidad. Una autorización puede realizarse para un centro concreto, lo que afecta a la visibilidad de borradores.

### Certificado 0035
Certificado de sello de aplicación utilizado para firmar documentos en nombre del sistema en solicitudes presenciales del tramitador.

### Checkbox
Componente que permite marcar una o varias opciones independientes de selección múltiple. Siempre son visibles con orientación vertical por defecto.

### Cliente de Tramitación
Aplicación desde la que el funcionario tramita y gestiona el expediente, incluyendo la tarea de "Estudio de documentación".

### Compositor de Formularios
Ver EraiKIT. Herramienta de diseño y configuración de formularios dinámicos que facilita la creación, edición, traducción y publicación de formularios.

### Componente
Diferentes estructuras que facilitan o simplifican de manera visual el guiado, la comprensión y la captura de datos en un formulario. Pueden ser organizativos, informativos o de captura de datos.

### Componente de Digitalización
Componente que permite escanear y subir documentos a Dokusi, firmándolos automáticamente.

### Componente Dirección / Dirección Postal
Componente específico para capturar datos de ubicación. Incluye subcomponentes como código postal, país, territorio histórico, municipio, localidad, dirección, número/bloque, escalera, piso, puerta, latitud, longitud.

### Concatenar
Acción que permite concatenar valores extraídos de uno o varios componentes del formulario o valores constantes.

### Condición
Regla lógica que evalúa datos introducidos para determinar si se muestra un elemento o se ejecuta una acción.

### Configuración Dinámica
Capacidad del orquestador de configurar los pasos a mostrar en base a la información del CCP para cada procedimiento-acción telemática.

### Consentimiento
Autorización expresa del ciudadano para que la Administración consulte determinados datos.

### contextSubmission
Contexto de presentación de solicitudes.

### Control y Validación
Componentes que facilitan la selección, validación y control de la información ingresada.

### CSV
Comma-Separated Values. Formato de archivo que permite exportar/importar datos de tablas.

## D

### Dashboard
Pantalla de gestión y consulta, como el Dashboard de SVTs donde se pueden consultar y catalogar servicios.

### Date / Date Picker
Componente selector de fecha que permite seleccionar una fecha o rango de fechas. Puede incluir selección de hora.

### dateModify
Función que calcula la suma o resta de días, meses o años a una fecha.

### Datos Específicos (Paso 2)
Paso del orquestador que muestra el formulario asociado al procedimiento-acción telemática para capturar información específica.

### Declaración Responsable
Expresión bajo responsabilidad de la persona solicitante del cumplimiento de requisitos necesarios para realizar una solicitud. Pueden ser condicionadas u obligatorias.

### Declaraciones Responsables (Paso 5)
Paso donde se muestran para chequeo las declaraciones responsables configuradas en el CCP.

### DEMO
Funcionalidad que permite la ejecución simulada de una solicitud utilizando el formulario en edición antes de publicarlo.

### Deserializar
Proceso de interpretar el contenido de un archivo de formulario para actualizarlo en la base de datos del compositor en el entorno destino.

### detailInfo
Estructura que contiene el detalle de la solicitud con todos los datos introducidos por el usuario.

### Dirección Editable
Configuración del componente dirección que permite introducir datos manualmente además del autocompletado.

### DNI
Documento Nacional de Identidad.

### Documentos (Paso 4)
Paso donde se gestionan los documentos a aportar a la solicitud según configuración del CCP.

### Documento Acreditativo de Representación
Documento necesario cuando se actúa como representante sin RdA o en solicitudes multiinteresado. Se clasifica con tipología "ejgv_d_apo_autorrepjuri".

### Documento de Autorización
Documento completado en solicitudes tramitadas por funcionario habilitado. Se clasifica con tipología "ejgv_d_Autorizacion".

### Documentos Asociados
Configuración de tabla que permite asociar documentos específicos a cada registro de la tabla en el paso 4.

### DOKUSI
Gestor documental corporativo de Gobierno Vasco donde se almacenan todos los documentos relacionados con la tramitación de solicitudes y expedientes.

## E

### EJIE
Eusko Jaurlaritzen Informatika Elkartea - Sociedad Informática del Gobierno Vasco, S.A.

### ejgvDocument
Elemento XML del esquema que contiene información de tramitación y negocio de una solicitud o acción telemática.

### ejgv_d_apo_autorrepjuri
Tipología de documento para acreditar representación jurídica.

### ejgv_d_Autorizacion
Tipología de documento para autorización de funcionario habilitado.

### ejgv_d_archivo_adjunto
Tipo genérico de archivo en el catálogo de documentos.

### Endpoint
URL o dirección del servicio web que se ejecutará para consumir un SVT.

### Entidad Financiera Colaboradora
Entidad bancaria colaboradora con la Administración. Se valida mediante IBAN.

### Entregados Anteriormente
Opción de aportación de documentos donde el ciudadano especifica datos de un documento entregado previamente (órgano, fecha, título) para que el tramitador lo localice.

### EraiKIT
Nombre del componente Compositor de Formularios. Herramienta de diseño y configuración de formularios dinámicos del Gobierno Vasco, solo disponible en entorno de desarrollo. Facilita la creación, edición, traducción y publicación de formularios mediante un editor visual (compositor gráfico).

### Esquema de Retorno
Configuración que define la estructura de respuesta de un SVT (valor simple, lista simple, clave-valor, tabla) permitiendo transformar XML/JSON a formato estándar interpretable.

### Estado
Situación en que se encuentra un formulario o SVT (borrador, publicado, vigente, no vigente, mock).

### Estudio de Documentación
Tarea del cliente de tramitación donde el funcionario marca qué datos o documentos deben subsanarse.

### Expediente
Conjunto de documentos y actuaciones relacionados con un procedimiento administrativo iniciado por un ciudadano. Identificado mediante Folder ID en los sistemas de tramitación.

### Expresión Regular
Patrón de validación de formato de datos.

## F

### FH / Funcionario Habilitado / Persona Funcionaria Habilitada
Funcionario público autorizado para rellenar solicitudes en nombre de ciudadanos. Se valida mediante certificado de "Personal de Entidades Públicas Vascas".

### Footer
Parte inferior de la interfaz que contiene funcionalidades de "Guardar borrador", "Volver" y "Guardar y continuar".

### Formato
Configuración específica de componentes según la naturaleza del valor (NIF/DNI, CIF, NIE, email, teléfono, IBAN, matrícula, etc.).

### Fórmula
Validación basada en reglas IF/ELSE creadas mediante operadores de comparación (=, <>, >, <, >=, <=) y puertas lógicas (AND, OR).

### Fragmento
Conjunto de componentes relacionados y configurados con validaciones, funciones y acciones que pueden reutilizarse en formularios. Pueden ser comunes o específicos.

### Fragmento Común
Fragmento gestionado por el grupo funcional "Platea-Tramitación", usable por todos los grupos. Se incorpora por referencia en formularios.

### Fragmento Específico
Fragmento gestionado por cada grupo funcional, usable sólo por ese grupo. Se incorpora por copia en formularios.

### Función
Regla de cálculo que se aplica a un componente como acción en base a una condición (suma, resta, multiplicación, división, cálculos de fecha).

## G

### getRequestInformation
Servicio web que permite consultar datos de tramitación y de negocio de una solicitud o acción telemática ya enviada.

### getTelActionDocumentList
Servicio del CCP que devuelve la lista de documentos configurados para una acción telemática y procedimiento.

### getProcedureTelActionForm
Servicio que recupera información del procedimiento desde el CCP.

### Giltza
Sistema de firma electrónica del Gobierno Vasco utilizado para autenticación y firma de documentos.

### GPS
Global Positioning System. Coordenadas geográficas (latitud, longitud) que pueden capturarse en el componente dirección.

### GRID
Componente que permite organizar elementos en la misma línea, permitiendo incluir dos componentes por línea bajo 3 posibilidades de distribución. Solo admite componentes Input, Select y Date.

### Grupo de Repetición
Componente que permite incluir más de 6 datos por registro cuando una tabla supera 6 columnas. Muestra cabecera con campos identificativos y pie con totales.

### Grupo Funcional
Agrupación de usuarios asociada a departamentos (Justicia, Educación, Hacienda, Cultura, Salud, etc.) que determina permisos de acceso y gestión.

## H

### Header / Cabecera
Parte superior de la interfaz que muestra información del organismo, órgano instructor, nombre del procedimiento, código, acción telemática, usuario conectado e idioma.

### Hidden
Campo oculto que almacena información no visible para el usuario (ej: validación de IBAN contra Entidad Financiera Colaboradora).

## I

### IBAN
International Bank Account Number. Formato de identificación de cuenta bancaria.

### ID_TIPO
Identificador del tipo de retorno de un SVT (UNIBASIC, MULTIBASIC, UNIDUPLA, MULTIDUPLA, TABLA).

### Identificación (Paso 1)
Paso donde la persona conectada incluye información sobre cómo actúa en la solicitud (para mí, para otro, como profesional, como funcionario habilitado).

### Idioma
Configuración multiidioma que debe incluir al menos castellano y euskera. Puede incluir inglés y francés.

### Imagen
Componente informativo que permite añadir imágenes desde PC (drag&drop o explorador). Pueden ser diferentes por idioma.

### Input
Campo de texto simple para ingresar datos. Puede configurarse como oculto, de solo lectura o con restricciones de tipo (texto, numérico, email, contraseña).

### Instancia
Identificador del entorno o momento en que se ejecuta una acción telemática.

### Interesado
Persona que tiene interés legítimo en un expediente. En solicitudes multiinteresado, múltiples personas actúan de forma conjunta.

### Intranet
Red privada del Gobierno Vasco donde se consumen los aplicativos backend.

### isPermissionCode
Parámetro que indica si un documento aparece en el bloque de autorizaciones "por Ley".

## J

### Jerarquía
Sección del compositor que permite añadir apartados, secciones, bloques y módulos, organizando el contenido de manera jerárquica.

### JSON
JavaScript Object Notation. Formato de intercambio de datos.

### Justificante de Solicitud
Documento generado tras el registro exitoso de una solicitud que se envía por correo electrónico.

## L

### Lista Clave-Valor (UNIDUPLA)
Tipo de retorno de SVT que devuelve un elemento con clave y valor.

### Lista Clave-Valores (MULTIDUPLA)
Tipo de retorno de SVT que devuelve un array de elementos clave-valor con varios valores por elemento.

### Lista Simple (MULTIBASIC)
Tipo de retorno de SVT que devuelve múltiples valores simples.

### Logos
Imágenes configuradas en el CCP que deben mostrarse en todas las páginas de la solicitud y en el PDF.

## M

### Metadatos
Datos adicionales necesarios para el almacenamiento de documentos en DOKUSI (ej: fecha, descripción, tipo).

### Mi Carpeta
Aplicación donde el ciudadano puede consultar sus solicitudes, borradores, plantillas y notificaciones.

### Mis Documentos
Repositorio personal de documentos del ciudadano en DOKUSI desde donde puede seleccionar documentos previamente aportados.

### Mock
Estado de un SVT que indica que no está expuesto ni es consumible. Se simula con una respuesta prefijada para permitir el diseño del formulario. Los formularios con SVTs en mock no pueden publicarse.

### Módulo
Componente organizativo de tercer nivel dentro de la jerarquía (Apartado > Sección > Bloque > Módulo).

### Módulo de Repetición
Componente módulo configurado para permitir añadir múltiples instancias durante la cumplimentación. Los componentes internos no pueden ser referenciados en validaciones condicionales.

### MUI
Material-UI. Biblioteca de componentes React utilizada para diseñar los estilos de los componentes.

### Multiinteresado
Configuración de procedimiento que permite identificar múltiples interesados que actúan de forma conjunta en una solicitud. Requiere firma de todos los interesados obligatorios.

### Multiselect
Componente Select que permite seleccionar múltiples elementos simultáneamente desde una lista.

## N

### Name
Nombre único que identifica un componente dentro del formulario.

### name-componente-label
Referencia a la etiqueta del elemento seleccionado en componentes de selección.

### name-componente-value
Referencia al valor introducido o seleccionado por el usuario en un componente.

### Navegador
Sección del compositor que muestra la estructura del formulario y permite reordenar elementos. Permite exportar el mapa del formulario en CSV.

### NIE
Número de Identidad de Extranjero.

### NORA
Servicio de normalización de direcciones del Gobierno Vasco utilizado para autocompletar direcciones postales.

### Notificación
Comunicación oficial de la Administración al ciudadano. Puede ser electrónica o postal.

## O

### OCR
Optical Character Recognition. Proceso de reconocimiento óptico de caracteres aplicado a documentos para extraer información automáticamente.

### OfficialForm
Formulario oficial.

### OID
Object Identifier. Identificador único de documento en DOKUSI.

### Operador de Comparación
Símbolo usado en fórmulas de validación (=, <>, >, <, >=, <=).

### Organismo
Entidad administrativa responsable del procedimiento (ej: Gobierno Vasco Seguridad).

### Órgano Instructor
Unidad administrativa que instruye el procedimiento (ej: Dirección de Tráfico).

### Orquestador / ToolkitBerria
Sistema encargado del proceso de tramitación de solicitudes y acciones telemáticas, adaptándose a las necesidades de cada procedimiento.

### OSB
Oracle Service Bus. Bus de servicios donde se exponen los SVTs.

### Otros Documentos
Bloque que permite incluir documentos genéricos que no están en tipos específicos configurados. Su aparición depende de la configuración en CCP.

## P

### Párrafo
Componente informativo que permite incluir texto enriquecido con formato.

### Paso
Cada una de las etapas secuenciales de cumplimentación de una solicitud, marcadas por el stepper.

### PDF
Portable Document Format. Formato de documento generado como resumen de la solicitud.

### personType
Tipo de persona en ejgvDocument (1:DNI, 2:CIF, 3:NIE, 4:Pasaporte, 5:Otros).

### Ping
Comprobación de conectividad con un servicio mediante llamada al endpoint.

### Plantilla
Solicitud prerellenada reutilizable que guarda información de identificación y datos específicos (pasos 1 y 2) con un nombre identificativo.

### PLATEA-TRAMITACIÓN
Grupo funcional administrador que puede ver y crear formularios de cualquier grupo funcional y gestiona fragmentos comunes.

### PPS / Proceso de Presentación de Solicitudes
Sistema que recibe y registra las solicitudes electrónicas enviadas desde el orquestador.

### PRE
Entorno de preproducción.

### Presencial de la Ciudadanía
Acción telemática donde el ciudadano completa una solicitud sin autenticarse, obteniendo un PDF con QR para presentar en oficinas.

### Presencial del Tramitador
Acción telemática donde el tramitador completa una solicitud iniciada por el ciudadano (en papel o electrónica).

### Pre-rellenado
Característica que completa automáticamente datos de una solicitud usando información de solicitudes anteriores del mismo procedimiento.

### Previsualizar
Funcionalidad que permite ver el resultado final del formulario antes de su publicación.

### PRO
Entorno de producción.

### Procedimiento
Conjunto de trámites y actuaciones que regula la gestión administrativa de un servicio o solicitud.

### Profesional
Perfil especial de usuario de determinados colectivos (instaladores eléctricos, empresas de gas) que requieren identificación específica en la solicitud.

### Properties
Archivo de propiedades donde residen listados de valores y configuraciones.

### Publicado
Estado de un formulario que permite su selección en CCP para asociarlo a una acción telemática. No puede editarse.

### Puerta Lógica
Operador lógico usado en validaciones (AND, OR).

## Q

### QR
Quick Response. Código bidimensional que identifica una presolicitud.

## R

### Radio Button
Componente de selección única entre pocas opciones visibles simultáneamente. Alineación horizontal por defecto si son 2 opciones.

### RAT
Código de recuperación de textos.

### RdA / Registro de Apoderamiento
Registro donde se almacenan las autorizaciones y representaciones entre personas y entidades.

### React
Biblioteca JavaScript para construir interfaces de usuario.

### Referencia
Modo de incorporación de fragmentos comunes en formularios, donde se crea un enlace al fragmento en lugar de copiar su contenido.

### Registro
Proceso de asignación de número oficial a una solicitud presentada.

### Registro de Interesados (RI)
Sistema que almacena datos de contacto de ciudadanos para comunicaciones con la Administración.

### Release
Cambio menor en un formulario que no añade nuevos campos y mantiene compatibilidad. Segundo número en el versionado (ej: v01.02).

### Representado
Persona o entidad en cuyo nombre actúa un representante.

### Representante
Persona que actúa en nombre de otra persona o entidad, con o sin autorización en RdA.

### REST
Representational State Transfer. Arquitectura de servicios web.

### Resumen y PDF (Paso 6)
Paso que presenta resumen de todos los datos incorporados, permite visualizar el PDF y proceder a la firma y envío.

### Reutilización de Dirección
Funcionalidad que permite trasladar la dirección postal del paso 1 a componentes dirección del paso 2 si cumplen criterios de compatibilidad.

### Revisión y Publicación
Paso del compositor que muestra visión en modo ejecución y permite crear DEMO. Tras publicar, el formulario no puede editarse.

### RRI
Registro de Representantes e Interesados. Sistema que almacena información de ciudadanos.

### Requerimiento
Notificación oficial del tramitador al ciudadano solicitando subsanación de documentos o datos de una solicitud. Incluye un documento adjunto que detalla los motivos y elementos a subsanar, con un plazo determinado para su corrección.

## S

### Sección
Agrupación visual funcional de información dentro de un apartado. Las secciones van encabezadas por un título.

### Select
Componente de lista desplegable para elegir opciones. Puede ser simple (una opción) o múltiple. Permite búsqueda si tiene muchas opciones.

### Sello de Aplicación
Firma automática realizada con el certificado 0035 en solicitudes presenciales del tramitador.

### Serializar
Proceso de convertir el contenido de un formulario en formato transportable para traspaso entre entornos.

### Servicio
Web service o API que expone funcionalidades para ser consumidas.

### SOAP
Simple Object Access Protocol. Protocolo de servicios web.

### Solicitud
Petición formal que inicia un procedimiento administrativo.

### Solicitante
Persona física o jurídica que autoriza a la persona conectada a realizar la solicitud en su nombre, o la propia persona conectada si tramita para sí misma.

### Stepper
Componente visual que marca el avance secuencial en la cumplimentación de la solicitud mostrando los pasos.

### Subsanación
Acción telemática especial donde el ciudadano corrige datos o documentos marcados como incorrectos por el tramitador.

### sum
Función que suma una serie de valores y asigna el total a un campo del formulario.

### SVT / Servicio de Validación de Terceros
Microservicio o API que ofrecen las aplicaciones departamentales para validar información o recuperar datos que faciliten el autocompletado de formularios.

## T

### Tabla
Componente que permite añadir filas con campos configurados y generar totales mediante operaciones. Limitado a 5-6 columnas máximo.

### Tabla de Datos (ID_TIPO=TABLA)
Tipo de retorno de SVT que devuelve múltiples registros con columnas tipificadas.

### Territorio Histórico
División administrativa de la CAPV (Álava, Bizkaia, Gipuzkoa).

### Text Area
Componente para recoger entradas largas y descriptivas que permite saltos de línea y mayor extensión.

### Texto Enriquecido
Formato de texto que permite aplicar listas, negrita, cursiva, subrayado, enlaces y estilos de título.

### Toolkit Berria ASI
Nombre completo del proyecto: Toolkit Berria - Atención a los Servicios de Información. Sistema completo que moderniza y centraliza la creación y gestión de formularios electrónicos de la Administración del Gobierno Vasco, facilitando la tramitación telemática completa de procedimientos administrativos. Compuesto por dos componentes principales: EraiKIT (Compositor de Formularios) y Orquestador (Sistema de ejecución).

### ToolkitBerria
Nombre del nuevo orquestador de solicitudes. Ver **Orquestador** y **Toolkit Berria ASI**.

### Tooltip
Información adicional que aparece al pasar el cursor sobre un ícono.

### Totales
Cálculos automáticos en tablas o grupos de repetición (suma, media aritmética, máximo, mínimo).

### Touched
Indicador que marca si un campo ha sido clickeado o interactuado por el usuario.

### Traducción
Paso del compositor que permite traducir literales a diferentes idiomas (mínimo castellano y euskera). Puede ser mediante exportación CSV o manual.

### Tramitador
Funcionario encargado de gestionar y tramitar expedientes.

### Traspaso
Proceso de transferencia de formularios y SVTs entre entornos (desarrollo, preproducción, producción).

## U

### UNIBASIC
Tipo de retorno de SVT que devuelve un valor simple (STRING, DATETIME, INTEGER, DECIMAL, BOOLEAN).

### UNIDUPLA
Tipo de retorno de SVT que devuelve un elemento clave-valor.

### URL
Uniform Resource Locator. Dirección de acceso a aplicaciones o servicios.

## V

### Validación
Comprobación de corrección de datos introducidos. Puede realizarse sobre el componente directamente o mediante condiciones.

### Valor Simple (UNIBASIC)
Tipo de retorno de SVT que devuelve un único valor tipificado.

### Versión
Cambio importante en un formulario que añade nuevos campos y modifica la información recogida. Primer número en el versionado (ej: v01).

### Versionado
Sistema de numeración de formularios compuesto por versión y release (ej: v01.02). Para SVTs también permite crear nuevas versiones sin afectar formularios existentes.

### Vigente
Estado de un formulario o SVT que está activo y puede ser utilizado.

## X

### XLNETS
Sistema de autenticación de usuarios del Gobierno Vasco.

### XML
eXtensible Markup Language. Formato de intercambio de datos estructurados.

## Z

### Zuzenean
Sistema de gestión de registros que digitaliza documentos presentados presencialmente.

---

**Total de términos:** 245+

**Nota:** Todos los términos han sido extraídos exclusivamente de la documentación funcional ASI (Análisis del Sistema de Información) del Toolkit Berria - Compositor de Formularios v1.4 y Orquestador v1.4, sin incluir términos específicos de procesos de negocio o casos de uso particulares.

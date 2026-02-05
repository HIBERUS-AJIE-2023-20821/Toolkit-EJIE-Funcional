Role: Actúas como Product Owner que trabaja con Jira.
Tarea: Generar Historias de Usuario con:
- Sección Como / Quiero / Para (una línea cada una).
- Descripción breve (≤200 palabras).
- Criterios de Aceptación claros en lenguaje natural.
- En los criterios de aceptación con lenguaje natural usa vocabulario binario en criterios: muestra/no muestra, permite/no permite, bloquea/no bloquea. Con bullets verificables.
- añade otra sección de con los mismos criterios en formato Gherkin (Given/When/Then)
- Estilo: Claro, conciso, orientado a equipos de desarrollo. Evita ambigüedades.
- Salida: Formato Markdown listo para pegar en Jira (un único bloque completo) con la siguientes caracteristicas:
  - Cada historia es un encabezado markdown de nivel 2 (##).
  - un bloque inicial como-quiero-para con bullets
  - una sección de Descripción que sea un encabezado markdown de nivel 3 (###) "Descripción" y uno o varios párrafos
  - una sección de Criterios de Aceptación que sea un encabezado markdown de nivel 3 (###) "Criterios de aceptación (lenguaje natural)" con bullets
  - una sección de Criterios en Gherkin que sea un encabezado markdown de nivel 3 (###) "Criterios en Gherkin" con bullets
- Idioma: Español (terminología Agile).
- No incluyas explicaciones fuera del bloque.
- Adapta el contenido teniendo en cuenta que es para un equipo de desarrollo de software ágil, con microservicios, una aplicacion frontal, y varios micros con api REST.
- Dividimos las historias, una para cada uno de los diferentes pasos que tiene el proceso: acceso, identificación de personas conectada y participantes (interesado, representante, autorizados), edición de campos, gestión de documentos, gestión de declaraciones responsables, pantalla de resumen, pdf de la solicitud y envío al sistema PPS.
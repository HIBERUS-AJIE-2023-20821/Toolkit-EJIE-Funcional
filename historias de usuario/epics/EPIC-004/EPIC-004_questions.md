# EPIC-004: Preguntas abiertas

## Preguntas de negocio

### 1. Prioridad de restricciones
Si un procedimiento tiene configurada limitación de unicidad Y el ciudadano ya aportó un documento del tipo desde "Documentos Entregados Anteriormente", ¿puede sustituirlo cargando uno desde dispositivo? ¿O debe primero eliminar el existente?

### 2. Mensajes de error personalizados
¿Deben personalizarse los mensajes de error según el tipo de restricción (unicidad, formato específico)? ¿Existe un catálogo de mensajes estándar por tipo de validación?

### 3. Formatos específicos vs formatos generales
Si un tipo de documento tiene formatos específicos configurados (por ejemplo, solo PDF), ¿prevalecen sobre los formatos generales? ¿O se suman ambas restricciones?

### 4. Validación en cliente vs servidor
¿Las validaciones de formato específico y unicidad deben realizarse solo en el navegador (cliente) o también en el servidor? ¿Qué ocurre si hay discrepancia?

### 5. Configuración por instancia de acción telemática
¿Los formatos específicos pueden variar según la instancia de la acción telemática? ¿O solo dependen del tipo de documento y procedimiento?

### 6. Sustitución de documento único
Cuando existe limitación de unicidad, ¿debe existir un botón explícito de "Sustituir documento" o el ciudadano debe eliminarlo y cargarlo nuevamente?

### 7. Visualización de formatos múltiples
Si un tipo de documento admite múltiples formatos específicos (por ejemplo: PDF, JPG, PNG), ¿cómo deben mostrarse al ciudadano? ¿Lista separada por comas, iconos, desplegable?

### 8. Cache de configuración
¿La configuración del CCP se consulta cada vez que el ciudadano accede al paso 4, o se cachea durante la sesión? ¿Qué ocurre si cambia la configuración mientras el ciudadano está tramitando?

### 9. Documentos ya aportados
Si el ciudadano retrocede del paso 5 al paso 4 y ya tiene documentos cargados, ¿la validación de unicidad permite mantenerlos o debe revisar desde cero?

### 10. Bloque "Otra documentación" condicionado por otros factores
Además de la configuración del procedimiento, ¿existen otros factores que puedan condicionar la visualización del bloque "Otra documentación" (rol del usuario, estado del expediente, etc.)?

### 11. Formato de extensiones en configuración
¿Cómo se almacenan las extensiones en el catálogo? ¿Con punto (.pdf) o sin punto (pdf)? ¿En mayúsculas o minúsculas?

### 12. Documentos obligatorios vs opcionales con formato específico
¿Los formatos específicos aplican tanto a documentos obligatorios como opcionales? ¿O solo a ciertos tipos de documentos?

---

*Documento creado: 28/01/2026*  
*Última actualización: 28/01/2026*

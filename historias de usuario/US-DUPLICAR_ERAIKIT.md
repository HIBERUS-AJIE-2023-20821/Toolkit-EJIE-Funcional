# US-036: Duplicación de componentes en el Compositor de Formularios

**Épica:** Pendiente de asignar - EraiKIT (Compositor de Formularios)

## Historia de usuario
**Como** diseñador de formularios  
**Quiero** poder duplicar un componente existente dentro del formulario  
**Para** agilizar la creación de formularios reutilizando la configuración ya definida en lugar de construir cada componente desde cero

## Descripción funcional
El Compositor de Formularios (EraiKIT) permite duplicar cualquier componente existente en el formulario. La duplicación genera una copia completa del componente, incluyendo toda su estructura interna y configuración.

**Identificación del duplicado**: Para evitar conflictos con identificadores y etiquetas existentes, el sistema modifica automáticamente los identificadores y etiquetas del componente copiado:
- **Primera copia**: se añade el sufijo `_copia` al ID y al label del componente y de todos sus componentes hijos
- **Copias sucesivas**: si ya existe un componente con sufijo `_copia`, se añade correlativo: `_copia2`, `_copia3`, etc.

**Configuración preservada**: Las validaciones, comportamientos y relaciones con otros campos y/o componentes del componente original se mantienen intactas en el duplicado.

**Posicionamiento**: El componente duplicado se inserta inmediatamente después del componente original en el formulario.

## Criterios de aceptación

### CA-1: Duplicación de componente simple
**Dado** que el diseñador tiene un componente en el formulario  
**Cuando** ejecuta la acción de duplicar sobre ese componente  
**Entonces** el sistema crea una copia completa del componente con toda su estructura  
**Y** la ubica inmediatamente después del componente original

### CA-2: Modificación de ID y label en la primera copia
**Dado** que el diseñador duplica un componente por primera vez  
**Cuando** el sistema genera el duplicado  
**Entonces** el ID del componente copiado tendrá el sufijo `_copia`  
**Y** el label del componente copiado tendrá el sufijo `_copia`

### CA-3: Modificación de IDs y labels en componentes hijos
**Dado** que el componente duplicado contiene componentes hijos  
**Cuando** el sistema genera el duplicado  
**Entonces** el ID de cada componente hijo tendrá el sufijo `_copia`  
**Y** el label de cada componente hijo tendrá el sufijo `_copia`  
**Y** la modificación se aplica en todos los niveles de la jerarquía

### CA-4: Numeración correlativa en duplicaciones sucesivas
**Dado** que ya existe un componente con sufijo `_copia` en el formulario  
**Cuando** el diseñador duplica el componente original de nuevo  
**Entonces** el nuevo duplicado tendrá el sufijo `_copia2`  
**Y** una tercera duplicación generará el sufijo `_copia3`  
**Y** así sucesivamente de forma correlativa

### CA-5: Preservación de validaciones
**Dado** que el componente original tiene validaciones configuradas  
**Cuando** el sistema genera el duplicado  
**Entonces** el componente copiado conserva todas las validaciones del original  
**Y** las validaciones funcionan de forma independiente en el duplicado

### CA-6: Preservación de comportamientos
**Dado** que el componente original tiene comportamientos configurados (mostrar/ocultar, habilitar/deshabilitar, etc.)  
**Cuando** el sistema genera el duplicado  
**Entonces** el componente copiado conserva todos los comportamientos del original  
**Y** los comportamientos actúan de forma independiente sobre el duplicado

### CA-7: Preservación de relaciones con otros campos y componentes
**Dado** que el componente original tiene relaciones configuradas con otros campos o componentes del formulario  
**Cuando** el sistema genera el duplicado  
**Entonces** el componente copiado conserva las referencias a esas relaciones  
**Y** las relaciones quedan activas en el duplicado

### CA-8: Unicidad de IDs en el formulario
**Dado** que el sistema genera el duplicado con sufijo `_copia`  
**Cuando** ya existe en el formulario un componente con ese ID resultante  
**Entonces** el sistema aplica el siguiente correlativo disponible (`_copia2`, `_copia3`, etc.)  
**Y** garantiza que todos los IDs del formulario son únicos tras la duplicación

---

*Historia creada: 25/02/2026*

# EPIC-006: Autorizaciones de consulta de datos

## Resumen / Objetivo de negocio
Permitir que los ciudadanos gestionen las autorizaciones para que la Administración consulte sus datos, evitando la aportación de documentación que ya obra en poder de otros organismos públicos, agilizando así el proceso de tramitación.

## Contexto
La Administración puede consultar datos del ciudadano que ya obran en su poder o en otras administraciones públicas para evitar que tenga que aportar documentación. Sin embargo, el ciudadano tiene derecho a oponerse a esta consulta o a no autorizarla, en cuyo caso deberá aportar la documentación correspondiente.

### Tipos de datos según su naturaleza jurídica

El CCP configura **3 tipos de autorizaciones** para cada procedimiento:

1. **Datos "por Ley" (mandatorio)**: La Administración puede consultar por mandato legal sin necesidad de autorización del ciudadano. **No se visualizan en la pantalla** pero **sí se incluyen automáticamente en la solicitud**.

2. **Datos "salvo oposición" (bajo autorización expresa)**: Datos cuya consulta está autorizada por defecto, pero el ciudadano puede oponerse selectivamente. **Se visualizan en pantalla** y requieren interacción.

3. **Datos "únicamente si consiente" (bajo consentimiento)**: Datos que requieren autorización explícita del ciudadano para cada uno. **Se visualizan en pantalla** y requieren interacción.

### Funcionamiento de la pantalla
La pantalla presenta una **pregunta global inicial** que facilita la decisión del ciudadano, seguida de dos bloques donde puede ajustar selectivamente cada dato:

**Pregunta global**: "¿Autorizas a la Administración a consultar tus datos?" (Radiobutton: Sí / No)

**Bloque 1 - Datos salvo oposición**:
- Switch general que afecta a todas las autorizaciones del bloque
- Checkbox individual por cada autorización que se puede consultar
- **Textarea para motivo de oposición**: Aparece cuando se marca oposición a cualquier autorización (obligatorio)
- Comportamiento: Si el usuario NO marca la oposición, la Administración puede consultar

**Bloque 2 - Datos únicamente si consiente**:
- Switch general que afecta a todas las autorizaciones del bloque
- Checkbox individual por cada autorización que requiere consentimiento expreso
- Comportamiento: Solo si el usuario marca explícitamente, la Administración puede consultar

### Lógica de interacción
1. **Estado inicial**: Ambos bloques aparecen **deshabilitados** hasta que el ciudadano responda a la pregunta global
2. **Si responde SÍ (global)**: Se habilitan ambos bloques con:
   - Bloque "salvo oposición": TODOS los checkboxes desmarcados (NO se opone a ninguno)
   - Bloque "únicamente si consiente": TODOS los checkboxes marcados (autoriza todos)
3. **Si responde NO (global)**: Se habilitan ambos bloques con:
   - Bloque "salvo oposición": TODOS los checkboxes marcados (se opone a todos)
   - Bloque "únicamente si consiente": TODOS los checkboxes desmarcados (no autoriza ninguno)
4. **Ajuste selectivo**: Una vez habilitados, el ciudadano puede marcar/desmarcar checkboxes individuales
5. **Motivo de oposición**: Si marca oposición a cualquier autorización (bloque 1), aparece un textarea obligatorio para especificar el motivo
6. **Sincronización automática**: Los radiobuttons globales y switches de bloque se ajustan automáticamente según la selección individual de checkboxes

### Consecuencias
- Las **autorizaciones "por Ley"** se incluyen automáticamente en la solicitud sin mostrarlas en pantalla
- Si el ciudadano se opone o no concede alguna autorización (tipos 2 y 3), los documentos relacionados aparecerán como **obligatorios en el Paso 4 (Documentos)**
- Las autorizaciones concedidas (tanto "por Ley" como las consentidas) la Administración las consultará directamente sin necesidad de que el ciudadano aporte documentación

## Historias relacionadas
- [US-016](US-016.md) - Presentación y visualización de autorizaciones
- [US-017](US-017.md) - Gestión de oposiciones y autorizaciones por autorización
- [US-018](US-018.md) - Sincronización, validación y registro de autorizaciones
- [US-019](US-019.md) - Visualización del motivo de oposición en Resumen y PDF/HTML
- [US-020](US-020.md) - Inclusión del motivo de oposición en el detailInfo del ejgvDocument

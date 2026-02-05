# Índice de Épicas e Historias de Usuario

## EPIC-001: Subsanación - Proceso del Ciudadano

Permite a los ciudadanos responder a requerimientos de subsanación de manera electrónica, aportando documentación o datos faltantes o incorrectos.

### Documentos de la épica
- [EPIC-001: Subsanación - Proceso del Ciudadano](epics/EPIC-001/EPIC-001.md) - Documento principal de la épica
- [EPIC-001: Preguntas y Supuestos](epics/EPIC-001/EPIC-001_questions.md) - Preguntas abiertas y supuestos

### Historias de Usuario

| ID | Título | Story Points | Descripción resumida |
|---|---|---|---|
| [US-001](epics/EPIC-001/US-001.md) | Acceso al proceso de subsanación | 5 | Acceder al proceso desde MiCarpeta con parámetros de expediente y requerimiento |
| [US-002](epics/EPIC-001/US-002.md) | Identificación de participantes | 3 | Visualizar y confirmar interesado y representante del expediente |
| [US-003](epics/EPIC-001/US-003.md) | Edición de campos requeridos | 8 | Editar campos marcados para subsanación con validaciones |
| [US-004](epics/EPIC-001/US-004.md) | Gestión de documentos | 8 | Adjuntar documentos requeridos con validación y almacenamiento en Dokusi |
| [US-005](epics/EPIC-001/US-005.md) | Gestión de declaraciones responsables | 5 | Aceptar declaraciones responsables obligatorias y opcionales |
| [US-006](epics/EPIC-001/US-006.md) | Pantalla de resumen | 5 | Revisar toda la información antes del envío definitivo |
| [US-007](epics/EPIC-001/US-007.md) | Generación de PDF y envío a PPS | 13 | Generar justificante y enviar subsanación al sistema de tramitación |

**Total Story Points**: 47

### Flujo del proceso

```
┌─────────────┐
│   US-001    │  Acceso desde MiCarpeta
│   Acceso    │
└──────┬──────┘
       │
       ▼
┌──────────────────────────────────────────┐
│  Pasos 2-5 (pueden completarse en        │
│  cualquier orden)                        │
│                                          │
│  ┌───────────┐  ┌─────────────┐        │
│  │  US-002   │  │   US-003    │        │
│  │Participan.│  │   Campos    │        │
│  └───────────┘  └─────────────┘        │
│                                          │
│  ┌───────────┐  ┌─────────────┐        │
│  │  US-004   │  │   US-005    │        │
│  │Documentos │  │Declaraciones│        │
│  └───────────┘  └─────────────┘        │
└──────────────┬───────────────────────────┘
               │
               ▼
        ┌──────────────┐
        │    US-006    │  Revisión final
        │   Resumen    │
        └──────┬───────┘
               │
               ▼
        ┌──────────────┐
        │    US-007    │  Envío definitivo
        │ PDF y Envío  │
        └──────────────┘
```

### Dependencias externas

- **MiCarpeta**: Control de acceso, validación de enlaces, datos de participantes
- **Sistema de autenticación**: Identidad del usuario
- **Dokusi**: Almacenamiento de documentos
- **CCP**: Catálogo de Configuración de Procedimientos
- **PPS/Tramitagune**: Sistema de gestión de expedientes
- **Compositor de Formularios**: Renderizado dinámico de formularios

### Criterios de éxito de la épica

- ✅ Al menos el 80% de las subsanaciones completadas electrónicamente
- ✅ Tiempo medio de completado < 10 minutos
- ✅ Tasa de éxito en envío a PPS > 98%
- ✅ Reducción de errores en documentación > 30%

---

## Convenciones de las historias de usuario

### Formato de IDs
- **Épicas**: EPIC-XXX
- **Historias de Usuario**: US-XXX
- **Preguntas/Supuestos**: EPIC-XXX_questions.md o US-XXX_questions.md

### Story Points
- 1-2: Muy simple, cambios mínimos
- 3-5: Simple a medio, funcionalidad clara
- 8: Complejo, requiere integración o lógica compleja
- 13: Muy complejo, múltiples integraciones o incertidumbre

### Estados de historia
- **Not Started**: Pendiente de iniciar
- **In Progress**: En desarrollo
- **In Review**: En revisión
- **Done**: Completada y aceptada

### Criterios de aceptación
- Formato Gherkin: Given/When/Then
- Al menos un escenario por caso feliz y casos de error
- Verificables y testeables

---

*Última actualización: 23/01/2026*

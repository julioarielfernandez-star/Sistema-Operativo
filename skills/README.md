# Skills — cómo se guardan y se mantienen

## La regla de las dos copias

Cada habilidad (skill) existe en dos lugares, con roles distintos:

1. **La fuente** vive acá, en `skills/<nombre-skill>/SKILL.md` — versionada en git. Es la única que se edita.
2. **La instalada** vive en Claude (en la cuenta de cada integrante, o compartida a nivel organización con plan Team). Es una copia de la fuente.

**Nunca se edita la instalada a mano.** El ciclo es: editar la fuente en el repo → aprobar (si es cambio de fondo, vía `CHG-<id>`) → reinstalar. Así git guarda el historial de cada regla y todos los integrantes trabajan con la misma versión.

## La cadena proceso → skill → rol

```
procesos/<proceso>.md      →  QUÉ se hace y en qué orden (el SOP, lo lee un humano)
skills/<skill>/SKILL.md    →  CÓMO lo ejecuta la IA (instrucciones operativas)
config/team-members.json   →  QUIÉN ocupa el rol que ejecuta ese proceso hoy
config/governance.json     →  QUÉ NUNCA se hace en automático (barreras)
```

Una skill por proceso. La skill cita a su proceso; el proceso cita a su skill. El conocimiento vive en el par proceso+skill, no en la persona.

## Convención de carpeta

```
skills/
├── README.md                    ← este archivo
├── _PLANTILLA-SKILL.md          ← plantilla para skills nuevas
└── <nombre-skill>/
    ├── SKILL.md                 ← la skill (frontmatter + instrucciones)
    └── recursos/                ← plantillas, ejemplos, scripts (si hacen falta)
```

Nombres en kebab-case, verbo primero, igual que el catálogo V3: `capturar-reclamos-gmail`, `liquidar-expensas`, `coordinar-mantenimiento`.

## Cómo se decide QUÉ skill construir (prioridad por impacto)

No se construye por lista: se construye por dolor. La fuente de priorización es
[`../procesos/registro-de-errores.md`](../procesos/registro-de-errores.md):

1. Cada error operativo se anota ahí (2 minutos: qué pasó, proceso, costo).
2. **Prioridad = impacto × frecuencia.** El proceso con más errores caros es el próximo a documentar + automatizar.
3. Regla de gobierno: 3 errores semejantes en 7 días — o 1 falla grave — disparan una propuesta de cambio con evidencia, riesgo y reversión.

## Ciclo de vida de cada skill

1. **Documentar** el proceso en `procesos/` (con quien lo hace hoy — 30 min de charla).
2. **Redactar** la skill desde ese proceso (con skill-creator).
3. **Piloto**: la usa UNA persona (la que ocupa el rol) durante 1–2 semanas, con las barreras de `governance.json` activas (nada sale hacia afuera sin humano).
4. **Medir**: ¿bajaron los errores de ese proceso en el registro?
5. **Compartir**: recién ahí se instala para el resto del equipo.
6. **Mejorar**: correcciones → registro de errores → propuesta CHG → editar la fuente → reinstalar.

# Sistema-Operativo

Repositorio central del sistema de administración, proyectos y automatización con IA de **Administración Julio Ariel Fernández**. Acá vive el conocimiento del sistema: arquitectura, procesos, configuración y reglas de gobierno. Los datos operativos viven en Google Drive/Sheets; las skills se ejecutan en Claude.

## Contenido

| Archivo | Qué es |
|---|---|
| [PLAN.md](PLAN.md) | Plan maestro: qué existe, arquitectura recomendada, fases de implementación |
| [docs/SISTEMA-V3.md](docs/SISTEMA-V3.md) | Arquitectura completa del Sistema V3 (fuentes, orquestador, 17 agentes, gobierno, barreras) |
| [docs/INVENTARIO.md](docs/INVENTARIO.md) | Inventario de todo lo construido: skills, conectores, Drive, planillas, equipo |
| [config/](config) | Configuración operativa: gobierno, horarios, catálogo de procesos, consorcios, equipo |
| [procesos/](procesos) | Un documento por proceso de trabajo (plantilla incluida) |

## Reglas de oro

1. Fuente de verdad única: si no está en Drive/Sheets, no existe. Este repo guarda el *cómo*; Drive guarda el *qué*.
2. El conocimiento vive en la skill/proceso, no en la persona que hoy ocupa el rol.
3. La IA propone, un humano aprueba: nada sale hacia afuera (mail, WhatsApp, borrado) en automático.
4. Cambios de fondo solo vía propuesta `CHG-<id>` aprobada por Julio; el silencio deja la propuesta pendiente.
5. Toda decisión de diseño se escribe en este repo — lo que queda solo en un chat, se pierde.

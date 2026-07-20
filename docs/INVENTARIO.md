# Inventario — Todo lo construido hasta hoy (actualizado 2026-07-19)

Qué existe, dónde vive y qué sirve. Relevado leyendo el Drive completo (incl. `Administracion/CLAUDE.md` y `00-NUCLEO/Traspaso-Sistema.md`), el artifact del Sistema V3 y las skills instaladas.

## 0. El panorama: tenés TRES sistemas construidos en paralelo

| Sistema | Qué es | Dónde vive | Estado |
|---|---|---|---|
| **BRÚJULA + GTD** (jun 2026) | Metodología personal: Covey + GTD, módulos 00-NUCLEO / 01-ADMINISTRACION / 02-PROYECTOS, captura desde Plaud | `Mi unidad/00-NUCLEO/` | Armado; **abandonado desde 2026-06-21** con conflicto GTD sin resolver |
| **Sistema local Windows** (2026) | Scripts Python `_organizador`: organizador OCR, informes, tablero de vencimientos, Paquetes IA, bases de convivencia + Tarea Programada semanal | `Administracion/_organizador/` (PC de Julio) | **En producción** |
| **Sistema V3** (jul 2026) | Diseño de agentes: orquestador, 17 skills, caso maestro, gobierno diario 18:30 | Repo privado V3 + artifact | Diseñado, piloto controlado |

Este repo (`Sistema-Operativo`) es el punto de unificación de los tres.

## 1. Documentos de diseño existentes

- **`Administracion/CLAUDE.md`** (Drive, 2026-06-16) — cerebro del módulo administración: mapa de carpetas, lista maestra de 23 consorcios con CUIT, automatización, vencimientos, convivencia, paquetes IA, reglas. → Volcado a [`DRIVE-ESTRUCTURA.md`](DRIVE-ESTRUCTURA.md).
- **`00-NUCLEO/Traspaso-Sistema.md`** (2026-07-11) — handoff completo del sistema personal: estado, decisiones, 42 tareas, pendientes.
- **`00-NUCLEO/Sistema-BRUJULA.md`** — metodología (5 capas, Revisión Semanal, Arranque Diario, 3 MIT).
- **`00-NUCLEO/MAESTRO-INDICE.md`** — índice global de los 3 módulos.
- **Artifact "Sistema V3 — Mapa de arquitectura"** (2026-07-13) → reconstruido en [`SISTEMA-V3.md`](SISTEMA-V3.md).
- **Repo privado V3** (`PROYECTO-SISTEMA-OPERATIVO-V3.md`, `RUNBOOK-V3.md`, `config/`, `state/`, `schema/`) — no accesible desde esta sesión. **Pendiente unificar.**
- **`Procedimientos/`** (Drive, Paola 2023 + 2026) — SOPs: mantenimiento correctivo, control de abonos, control de ascensores, armado de liquidaciones, seguimiento WhatsApp/mail, template y checklist de nuevo consorcio.

## 2. Skills de Claude (instaladas o referenciadas)

| Skill | Estado | Equivalente V3 |
|---|---|---|
| `organizar-consorcios` | instalada (el script bueno es `organizar_real.py`) | `organize-administration-documents` |
| `redaccion-acta-de-asamblea` | instalada | `prepare-legal-assemblies` |
| `redaccion-convocatoria-de-asamblea` | instalada | `prepare-legal-assemblies` |
| `redaccion-de-comunicaciones` | instalada | `prepare-team-handoffs` |
| `tablero-vencimientos-sheets` | instalada | `monitor-recurring-due-dates` |
| `morning` | instalada | Resumen matutino 08:30 |
| `responder-whatsapp` | referenciada en CLAUDE.md (no visible en esta sesión) | `capture-whatsapp-cases` |
| `notebooklm` | referenciada en CLAUDE.md | consultas con cita |
| `procesa-bandeja` | referenciada en LEEME-GTD; **no encontrada** — confirmar si existe | motor GTD |

## 3. Conectores activos

Gmail · Google Calendar · Google Drive · Slack · Plaud.

## 4. Automatización local (PC Windows)

Ver detalle en [`DRIVE-ESTRUCTURA.md`](DRIVE-ESTRUCTURA.md): `organizar_real.py` (OCR, simulación/mover), `informe_panorama.py`, `informe_mantenimiento.py` (tablero HTML con semáforo), `generar_paquetes.py` (Paquetes IA por consorcio, Tarea Programada lunes 8:00), `construir_corpus.py` / `ocr_pendientes.py` (convivencia).

⚠️ Dependencia: todo esto corre en la PC de Julio. Si la PC no está prendida, no corre. Candidato natural a migrar a la nube (sesiones remotas de Claude / Routines) cuando se unifique.

## 5. Datos operativos

- **23 carpetas de consorcio** + lista maestra con CUIT → [`../config/consorcios.json`](../config/consorcios.json). Trackers mencionan ~31 unidades: confirmar altas/bajas.
- **Planillas clave** (`Archivos Gestión/`): Abonos Control de vtos (estado por color), Vtos. de servicios y abonos 2026 (pagos), Reporte proveedores por rubro, legajos, contratos ascensores.
- **GTD**: 42 tareas capturadas (T-001…T-042) en `GTD/Tareas (2).md` — ⚠️ los canónicos están vacíos por conflicto de sync; consolidar con aprobación de Julio.
- **Bases de convivencia**: EBA15 completa (+plugin); resto pendiente de corpus/OCR.
- **Paquetes IA**: uno por consorcio, regenerados semanalmente. Incluyen material sensible: solo uso interno.

## 6. Equipo

Ver [`../config/team-members.json`](../config/team-members.json): Ariel (titular), Paola (socia y co-administradora), Martín (recepción), Laura (cobranzas + sitio propio), Juan (técnica), Nacho (escaneo/sistemas), Andrea (conciliaciones); 4 cuentas Google satélite; apoyo externo (1 asociado, 3 estudios contables, 3 jurídicos). Panel y matriz de responsabilidades en `00. Administracion/00. Equipo/`.

## 7. Pendientes de unificación (en orden)

1. **Resolver el conflicto GTD** (`Tareas.md`/`Bandeja.md` vacíos vs copias `(1)`/`(2)`) — decisión de Julio, es el bloqueo del sistema personal desde el 21/06.
2. **Acceso al repo privado V3** o copiar sus documentos acá.
3. **Confirmar lista real de consorcios** (23 carpetas vs ~31 en trackers).
4. Confirmar si `procesa-bandeja` y `responder-whatsapp` existen como skills instalables.
5. Decidir qué automatización local migra a la nube y cuál queda en la PC.
6. Revisar las 42 tareas GTD (la mayoría con vencimientos de junio ya pasados).

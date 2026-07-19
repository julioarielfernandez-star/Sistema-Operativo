# Inventario — Todo lo construido hasta hoy (relevado 2026-07-19)

Qué existe, dónde vive y qué sirve. Este es el punto de partida para consolidar todo en este repo.

## 1. Diseño del sistema

- **Artifact "Sistema V3 — Mapa de arquitectura"** (2026-07-13): diseño completo del sistema — 5 fuentes, orquestador con checkpoints C0–C9, 8 agentes de ciclo de vida, 9 agentes de dominio, gobierno diario 18:30, 6 automatizaciones, barreras de seguridad. Reconstruido en [`docs/SISTEMA-V3.md`](SISTEMA-V3.md).
- **Repo privado V3** (no accesible desde esta sesión): contiene `PROYECTO-SISTEMA-OPERATIVO-V3.md`, `RUNBOOK-V3.md`, `config/*.json`, `state/state-v3.json`, `schema/v3.sql`. **Pendiente:** dar acceso a ese repo o copiar esos archivos acá para unificar.
- **Sitio de cobranzas de Laura**: repo propio, sincroniza por `receiptId`.

## 2. Skills de Claude instaladas (operativas hoy)

| Skill instalada | Equivalente en V3 |
|---|---|
| `organizar-consorcios` | `organize-administration-documents` |
| `redaccion-acta-de-asamblea` | parte de `prepare-legal-assemblies` |
| `redaccion-convocatoria-de-asamblea` | parte de `prepare-legal-assemblies` |
| `redaccion-de-comunicaciones` | `prepare-team-handoffs` (respuesta externa) |
| `tablero-vencimientos-sheets` | `monitor-recurring-due-dates` (visualización) |
| `morning` | Resumen matutino 08:30 |

## 3. Conectores activos en Claude

Gmail · Google Calendar · Google Drive · Slack · Plaud.

## 4. Google Drive — estructura real

- Carpeta raíz **`Administracion`** (desde 2016), con carpetas numeradas por consorcio: `305. EBA02`, `306. EBA09`, `35. …` (M5865), etc.
- Subcarpetas típicas: `Compartido`, `Seguimientos`, `Presupuestos`, `Comprobantes`, por tema (`Ascensores`, `Impermeabilización en terrazas`…).
- Convención de códigos: `V30` (Vedia 30), `M5865` (Av. Mitre 5865), `EBA02/09/10/15` (sectores Estación Buenos Aires). Archivos de comprobantes: `Comprobantes_M5865_Periodo_2026-06.pdf`.
- Carpeta **`Ordenar`** (2026-07): bandeja de entrada de documentos sueltos → la procesa `organizar-consorcios`.
- **Planillas activas**: `Mantenimiento Correctivo (Respuestas)` (formulario → sheet, con historial Trello 2024), `Reclamos EBA15 (Respuestas)`, `ResumenLiquidaciones - <periodo> - <cod>` (rendiciones anuales por consorcio), porcentajes de prorrateo por consorcio.
- **Legado Trello (2024)**: tableros por consorcio (Objetivos, Tarjetas, Documentos, Visitas, Etiquetas), hoy descartados. El historial quedó en la planilla de Mantenimiento Correctivo.

## 5. Cuentas y equipo detectados

| Cuenta / persona | Rol observado |
|---|---|
| julioarielfernandez@gmail.com | Titular (RPA 48/10921, CUIT 20-28477675-6) |
| soporte.julioarielfernandez@gmail.com | Cuenta satélite — comprobantes y liquidaciones |
| proveedores.julioarielfernandez@gmail.com | Cuenta satélite — proveedores |
| paolamfranco@gmail.com | Colaboradora (carpetas compartidas, pagos) |
| andrea.isabel.fernandez@gmail.com | Colaboradora (conciliaciones bancarias) |
| Laura | Cobranzas — sitio propio |
| martinezc.laboral@gmail.com | Asesoría laboral (externa) |

*(Roles a confirmar por Julio; ver `config/team-members.json`.)*

## 6. Qué falta traer / decidir

1. **Acceso al repo privado V3** desde estas sesiones (o copiar sus documentos a este repo) para no mantener dos versiones.
2. Confirmar roles y permisos reales del equipo (`config/team-members.json`).
3. Confirmar el catálogo de consorcios con sus códigos (`config/consorcios.json`).
4. Las conversaciones de chat anteriores no son recuperables directamente; solo sobrevive lo que quedó en artifacts, Drive, skills o repos. **Regla nueva: toda decisión de diseño se escribe en este repo.**

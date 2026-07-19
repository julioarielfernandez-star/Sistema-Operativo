# Sistema V3 — Arquitectura del sistema operativo administrativo

> Reconstruido desde el artifact "Sistema V3 — Mapa de arquitectura" (última revisión de contenido: 2026-07-12).
> Documentos fuente originales: `PROYECTO-SISTEMA-OPERATIVO-V3.md`, `RUNBOOK-V3.md`, `config/*.json` (repo privado V3).

**Principio rector:** Entrada → caso maestro → proceso/skill → rol requerido → integrante actual → evidencia y seguimiento. **El conocimiento vive en la skill, no en la persona que hoy ocupa el rol.**

Estado declarado: 18 skills · 6 automatizaciones activas · `state/state-v3.json` como ledger autoritativo · cambios de fondo solo vía `CHG-<id>` aprobado por Julio.

---

## 01 · Fuentes

| Código | Fuente | Regla |
|---|---|---|
| WA | WhatsApp Web | Un solo controlador, con lock |
| GM | Gmail | Nunca envía en automático |
| PL | Plaud | Solo Julio Ariel Fernández |
| CAL | Google Calendar | Recordatorio, no fuente de verdad |
| WEB | Sitio cobranzas Laura | Repo propio · sync por `receiptId` |

## 02 · Orquestador — `govern-administration-system`

Programa ciclos, mantiene el caso maestro, impide duplicados, controla locks y checkpoints, mide resultados y prepara decisiones para Julio. **No ejecuta trabajo de dominio ni cambia el sistema por iniciativa propia.**

Checkpoints del ciclo:

```
C0 CONFIG → C1 PREFLIGHT → C2 CAPTURE → C3 CASE → C4 PROPOSAL →
C5 APPROVAL → C6 APPLY → C7 READBACK → C8 RECONCILE → C9 CLOSE
```

## 03 · Agentes de ciclo de vida (8)

Capturan, clasifican, enrutan y cierran — sin ejecutar el procedimiento de dominio.

| Skill | Responsabilidad |
|---|---|
| `capture-whatsapp-cases` | Identidad exacta, nota de cliente, archivo verificado |
| `triage-gmail-inbox` | Etiquetas, borradores de hilo, archivo verificado |
| `extract-plaud-julio-actions` | Acciones y decisiones solo de Julio |
| `classify-eisenhower-cases` | Q1–Q4, SLA y fundamento |
| `route-administration-work` | Elige proceso y rol antes de la persona |
| `prepare-team-handoffs` | Handoff interno y respuesta externa por separado |
| `plan-calendar-reminders` | Recordatorios en el calendario exclusivo |
| `audit-reconcile-cases` | Coherencia, duplicados, reaperturas, cierres |

## 04 · Agentes de dominio (9)

Cada caso es una instancia de trabajo sobre una skill permanente, nunca una skill nueva.

| Skill | Dominio |
|---|---|
| `manage-treasury-payroll-tax` | Bancos, pagos, nómina, tributos |
| `manage-expenses-collections` | Liquidaciones, cobranzas, saldos |
| `manage-supplier-invoices` | Facturas, validación, derivación a pago |
| `coordinate-maintenance-providers` | Reclamos, visitas, presupuestos |
| `manage-insurance-contracts` | Pólizas, siniestros, renovaciones |
| `manage-hr-cleaning-compliance` | Personal, medicina laboral, limpieza |
| `prepare-legal-assemblies` | Mediaciones, convocatorias, actas |
| `organize-administration-documents` | Clasificación reversible por consorcio |
| `monitor-recurring-due-dates` | Abonos y obligaciones recurrentes |

## 05 · Config · Estado · Esquema

- `config/`: process-catalog · role-assignments · governance · policies · priority-thresholds · emergency-policy · routine-schedule · team-members · agents.json
- `state/`: `state-v3.json` (ledger autoritativo) · `governance-state.json` · `approved-baseline.json` (hashes aprobados) · `state-v2.json` (snapshot legado). ⚠️ Datos reales de clientes y pagos — repo privado.
- `schema/`: `v3.sql` (procesos, asignaciones, locks, métricas) · `v2.sql` (legado)

## 06 · Gobierno diario — 18:30 (America/Buenos_Aires)

Revisión diaria que cubre:

- Salud y cobertura por fuente
- Q1–Q4, vencidos, próximas 24 h, casos sin responsable
- Operaciones propuestas `OP-…` y cambios `CHG-…`
- Evidencia, riesgo, prueba y reversión de cada propuesta
- Excepciones, `needs_reopen` y escrituras inciertas

**Regla de aprobación:** el silencio deja la propuesta *pendiente*. Solo `APROBAR CAMBIO CHG-<id>` autoriza modificar skill, rol, horario, plantilla, umbral o permiso.

**Ciclo de mejora:** una corrección de caso no crea regla general. Tres correcciones semejantes en 7 días — o una falla grave — generan una propuesta con evidencia, regla actual, cambio, riesgo y reversión. Solo tras aprobación, el cambio baja a `config/` y de ahí a las skills.

## 07 · Automatizaciones (6)

| Automatización | Horario | Estado |
|---|---|---|
| WhatsApp | 08–19 h · cada hora | piloto |
| Gmail | 08–19 h · cada hora :20 | piloto |
| Seguimiento local | 08–19 h · cada 30 min | piloto |
| Plaud de Julio | 08:30 · 13:30 · 17:30 | piloto |
| Resumen matutino | 08:30 | activo |
| Gobierno y auditoría | 18:30 | activo |

## 08 · Barreras de seguridad

| Barrera | Valor |
|---|---|
| Envío WhatsApp interno/externo | `false` — nunca sin aprobación puntual |
| Envío Gmail | `false` — nunca sin aprobación puntual |
| Borrado | `false` — nunca sin aprobación puntual |
| Etiqueta / nota / borrador de hilo | piloto |
| Archivo de fuente verificada | piloto + readback |
| Calendar write | id explícito, nunca `primary` |

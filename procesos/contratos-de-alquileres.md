# Contratos de alquileres — control de tiempos

> **BORRADOR SEMILLA** — completar en entrevista de 30 min con quien lo opera hoy.
> Falla declarada (2026-07-20): se pierden los tiempos (vencimientos, renovaciones, ajustes).

- **Dominio:** vencimientos recurrentes / contratos
- **Skill asociada (a crear):** `controlar-contratos-alquileres`
- **Rol requerido:** a definir (¿Paola? ¿Julio?)
- **Frecuencia:** control mensual + alertas por hito
- **Aprueba:** Julio (notificaciones a inquilinos/propietarios siempre con revisión humana)

## Los hitos que NO se pueden pasar (típicos en Argentina — confirmar cuáles aplican)

| Hito | Anticipación necesaria | Por qué importa |
|---|---|---|
| Ajuste del canon (ICL/IPC/pactado) | aviso 30 días antes | Plata que se pierde cada mes de atraso |
| Vencimiento del contrato | 90–120 días antes | Decidir renovación/rescisión, notificar en plazo legal |
| Renovación: negociación de valores | 60 días antes | Sin margen se renueva mal o queda vacío |
| Actualización de garantías/seguros de caución | al renovar | Cobertura caída = riesgo total |
| Aumento de expensas extraordinarias que afectan al inquilino | al ocurrir | Conflictos por retroactivos |

## Preguntas para completar el proceso (entrevista)

1. ¿Cuántos contratos de alquiler se administran y dónde está la lista hoy? (¿planilla? ¿carpetas por consorcio? ¿cabeza de alguien?)
2. ¿Son unidades propias de clientes (administración de alquileres) o espacios de consorcios (cocheras, locales, antenas, medianería)?
3. ¿Qué índice de ajuste usa cada contrato y con qué frecuencia?
4. ¿Quién hace hoy el seguimiento y dónde anota?
5. Últimos 3 errores concretos: ¿qué contrato, qué se venció, qué costó?

## Automatización propuesta (v1 — la más simple que elimina el error)

1. **Planilla maestra "Contratos"** en Sheets: una fila por contrato — unidad, partes, inicio, fin, índice de ajuste, frecuencia, próximo hito, responsable, estado.
2. La skill `tablero-vencimientos-sheets` (ya instalada) la lee → tablero con semáforo.
3. Revisión automática semanal: qué hito cae en los próximos 30/60/90 días → aviso a Julio + borrador de la notificación correspondiente (nunca se envía sola).
4. Cada renovación cerrada actualiza la fila. Si un hito pasa sin acción → error 🔴 al registro.

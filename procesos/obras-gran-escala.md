# Obras de gran escala — pagos y autorizaciones del consejo

> **BORRADOR SEMILLA** — completar en entrevista.
> Falla declarada (2026-07-20): control de trabajos grandes, sus pagos y las autorizaciones del consejo de propietarios.

- **Dominio:** mantenimiento y proveedores / tesorería
- **Skill asociada (a crear):** `controlar-obras-gran-escala`
- **Rol requerido:** técnica (Juan) + pagos (Paola) + aprobación consejo
- **Aprueba:** consejo de propietarios (por acta o conformidad escrita) antes de cada etapa de pago

## Qué existe hoy en Drive (relevado)

- Comparativas de presupuestos por obra: ej. "Resumen Ejecutivo de Presupuestos - Consejo de Propietarios" (impermeabilización Torre 13: Lemos $24,5M / Montaño ~$12,6M / Brizuela $86M+IVA; videovigilancia; pintura de halls).
- Carpetas `NN. Presupuestos` por consorcio con los PDF de cada proveedor.
- Condiciones de pago pactadas por anticipo + cuotas (ej. Montaño: 30% inicio + 6 cuotas).

## El riesgo que hay que eliminar

Una obra grande tiene 3 cadenas que hoy corren sueltas: **avance físico** (¿se hizo?), **pagos** (¿cuánto se pagó y cuánto falta?) y **autorización** (¿el consejo aprobó ESTA etapa por escrito?). El error caro es pagar una cuota sin verificación del avance, o avanzar una etapa sin autorización documentada del consejo — eso deja al administrador expuesto personalmente.

## Ficha de obra (una por obra, propuesta v1)

`NN. <Consorcio>/NN. Obras/<obra>/FICHA-OBRA.md` + fila en planilla maestra "Obras":

- Consorcio · obra · proveedor elegido · presupuesto aprobado · fecha y acta/nota de aprobación del consejo
- Plan de pagos: cuota, monto, condición ("contra avance X"), autorización del consejo (link), comprobante (link), estado
- Avances verificados: fecha, quién verificó, fotos
- Desvíos: adicionales pedidos vs aprobados

## Regla de oro propuesta

**Ningún pago sin dos links en su fila: la autorización del consejo y la verificación del avance.** Si falta uno, el pago no sale y se genera aviso.

## Preguntas para la entrevista

1. Obras activas hoy: ¿cuáles, en qué consorcio, en qué etapa?
2. ¿Cómo documenta hoy el consejo sus aprobaciones? (¿acta? ¿WhatsApp? ¿mail?) ← si es WhatsApp, ahí está el agujero
3. Últimos errores concretos: ¿pago adelantado? ¿etapa sin autorización? ¿adicional no aprobado?
4. ¿Quién verifica avance físico y cómo queda registrado?

## Automatización propuesta (v1)

1. Planilla maestra "Obras" + ficha por obra (arriba).
2. Revisión semanal automática: cuotas próximas sin autorización o sin verificación → alerta 🔴 a Julio y Paola.
3. Skill que arma el resumen ejecutivo comparativo de presupuestos para el consejo (ya hay ejemplos del formato en Drive) y el texto de solicitud de conformidad.

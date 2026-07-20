# Control de costos de proveedores

> **BORRADOR SEMILLA** — completar en entrevista.
> Falla declarada (2026-07-20): los costos de proveedores no se controlan/comparan sistemáticamente.

- **Dominio:** facturas de proveedores / mantenimiento
- **Skill asociada (a crear):** `controlar-costos-proveedores`
- **Rol requerido:** técnica/proveedores (Juan) + pagos (Paola)
- **Aprueba:** Julio para desvíos sobre umbral

## Qué existe hoy en Drive (relevado)

- `Archivos Gestión/Reporte Rubro proveedores por consorcio.xlsx` — proveedores por rubro y consorcio.
- Cuenta `proveedores.julioarielfernandez@gmail.com` con vencimientos de pagos (planilla `Vtos. de servicios y abonos 2026`).
- Historia de precios dispersa en los PDF de presupuestos y en las liquidaciones mensuales.

## El error típico a eliminar

Pagar de más sin darse cuenta: el mismo rubro cuesta distinto en dos consorcios sin razón, un abono aumenta arriba de inflación sin renegociar, o se contrata sin comparar porque "siempre fue este proveedor".

## Controles propuestos (v1)

1. **Precio de referencia por rubro**: planilla "Costos" — rubro, proveedor, consorcio, importe, fecha, unidad (por mes / por visita / por m²). Se alimenta de cada factura/presupuesto nuevo.
2. **Alerta de desvío**: mismo rubro con diferencia > X% entre consorcios, o aumento interanual > índice de referencia → aviso para renegociar.
3. **Regla de las 2 cotizaciones**: por encima de un monto umbral (definir con Julio), no se contrata sin al menos 2 presupuestos comparados (la skill arma el cuadro comparativo, como los que ya existen para obras).
4. **Revisión trimestral de abonos**: los contratos recurrentes (ascensores, limpieza, matafuegos…) se comparan contra el mercado una vez por trimestre.

## Preguntas para la entrevista

1. ¿Umbral de monto a partir del cual exigir 2+ presupuestos?
2. ¿Qué rubros duelen más hoy? (¿ascensores? ¿plomería? ¿limpieza?)
3. Últimos errores concretos: ¿qué se pagó de más, dónde, cuánto?
4. ¿Quién carga las facturas hoy y en qué momento (ideal para capturar el precio)?

# Liquidación mensual de expensas

- **Dominio:** Expensas y cobranzas
- **Skill asociada:** `manage-expenses-collections` (V3; hoy manual + planillas)
- **Rol requerido:** administración / colaboradora de liquidaciones
- **Frecuencia:** mensual, por consorcio
- **Aprueba:** Julio antes de publicar y enviar

## Disparador

Cierre del período (fin de mes) de cada consorcio.

## Pasos (relevados — completar/ajustar)

1. Reunir comprobantes del período (cuenta soporte: `Comprobantes_<COD>_Periodo_AAAA-MM.pdf` en `<nro>. Comprobantes/<COD> - AAAA/`).
2. Cargar sueldos y cargas sociales (encargados según CCT 589/10: sueldo, antigüedad, plus, SAC, aportes ARCA/SUTERH/FATERYH).
3. Cargar pagos de suministros, servicios, abonos y seguros del período.
4. Conciliar con el extracto bancario (proceso de Andrea: planilla de conciliación, diferencia debe dar 0).
5. Aplicar porcentajes de prorrateo por unidad (planilla `Porcentajes <COD>`).
6. Generar la liquidación (sistema de expensas, formato Ley 14.701 PBA / Ley 941 CABA según jurisdicción).
7. Revisión y aprobación de Julio.
8. Publicar y notificar; actualizar `ResumenLiquidaciones - <periodo> - <COD>` (rendición anual).

## Datos y archivos

- Comprobantes: carpeta `Comprobantes` por consorcio (cuenta soporte).
- Conciliaciones: carpetas `<COD> - CONCILIACIONES`.
- Rendición anual: `ResumenLiquidaciones - AAAA-MM - <COD>.xlsx`.

## Reglas y límites

- Nada se envía a propietarios en automático (`gmail_send: false`).
- La conciliación bancaria debe cerrar en 0 antes de publicar.

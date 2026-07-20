# Gestión de cuestiones de convivencia

> **BORRADOR SEMILLA** — completar en entrevista.
> Falla declarada (2026-07-20): la gestión de casos de convivencia entre vecinos falla.
> **Es el proceso con mejor infraestructura ya construida** — el problema es el circuito del caso, no el conocimiento.

- **Dominio:** convivencia / legales
- **Skill asociada (a crear):** `gestionar-casos-convivencia` (la parte de conocimiento ya existe)
- **Rol requerido:** recepción (Martín) deriva → resuelve rol según gravedad; legales desde Carta Documento = solo Ariel y Paola
- **Aprueba:** Julio toda comunicación formal a propietarios

## Qué existe hoy (relevado — mucho)

- **Protocolo de respuesta**: `_organizador/convivencia/PROTOCOLO-CONVIVENCIA.md` — identificar consorcio → leer base sintetizada o corpus → responder citando documento + artículo + fecha.
- **Bases de convivencia** por consorcio (`NN. Base Convivencia` con `corpus/` + `INDICE-FUENTES.md`): EBA15 (307) completa + plugin compartible; el resto pendiente de corpus/OCR (`construir_corpus.py --todos`).
- **Regla jurídica clave** (de tu CLAUDE.md): los PRO.CRE.AR (EBA02/09/10/15, prob. Palmas del Sol) son fideicomiso/consorcio de hecho → multa = herramienta de gestión, no título ejecutivo; camino: intimación → mediación → justicia (art. 2069 CCCN). Los PH constituidos sí sancionan por reglamento.

## Lo que falta: el CIRCUITO del caso

El conocimiento (qué dice el reglamento) está resuelto. Lo que falla es el seguimiento: un reclamo de convivencia entra por WhatsApp o mail, se responde… y no queda caso abierto con estado, plazo y próximo paso. Resultado: reclamos que se repiten, escalan o se olvidan, y vecinos que sienten que "la administración no hace nada".

## Circuito propuesto (v1)

1. Todo reclamo de convivencia → **fila en planilla Casos**: fecha, consorcio, unidad, quién reclama, contra quién, tema, gravedad, estado, próximo paso, plazo.
2. Escala de tratamiento estándar: 1º comunicación informal → 2º nota formal citando reglamento (con la base de convivencia) → 3º intimación → 4º mediación/legales (solo Ariel+Paola).
3. La skill redacta cada pieza citando documento+artículo (protocolo existente) y registra el paso en el caso.
4. Revisión semanal: casos sin movimiento > 14 días → alerta.

## Preguntas para la entrevista

1. ¿Por dónde entran hoy los reclamos de convivencia y quién los recibe? (¿Martín?)
2. Últimos 3 casos que escalaron mal: ¿qué pasó, qué faltó?
3. ¿Qué consorcios generan más casos? (para priorizar sus bases de convivencia después de EBA15)
4. ¿Plazos estándar por gravedad? (respuesta al reclamante, intimación, escalamiento)

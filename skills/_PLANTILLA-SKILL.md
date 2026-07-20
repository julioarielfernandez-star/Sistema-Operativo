---
name: <nombre-skill>
description: <Cuándo debe activarse esta skill: qué pide el usuario, qué palabras la disparan, qué produce. Escribirla pensando en que Claude la elija correctamente.>
---

# <Nombre de la skill>

- **Proceso asociado:** `procesos/<proceso>.md` (leerlo si hay dudas de fondo)
- **Rol que la usa:** <rol, no persona — ver config/team-members.json>
- **Barreras:** nunca enviar mails/WhatsApp, nunca borrar, nunca exponer contenido de `NN. No compartido` (ver config/governance.json)

## Contexto que necesita

- Consorcio: identificarlo por código/alias (ver config/consorcios.json)
- Datos: <planilla o carpeta de Drive donde se lee>

## Pasos

1. …
2. …
3. Presentar el resultado como BORRADOR para revisión humana. Nunca enviarlo.

## Salida

- Formato: <documento / fila en planilla / borrador de mail>
- Se guarda en: <carpeta destino, convención `NN - Tema - AAAA-MM-DD - Descripción`>

## Errores conocidos y cómo evitarlos

- <error frecuente del registro> → <regla para no repetirlo>

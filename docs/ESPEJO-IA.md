# Espejo IA — Cómo ChatGPT y Gemini usan el sistema

## El diseño

ChatGPT y Gemini no pueden leer el repositorio GitHub, pero sí leen Google Drive. Por eso el sistema
mantiene un **espejo del repo en Drive**, con el mismo criterio que los "Paquetes IA" por consorcio:

```
Repo GitHub (fuente de verdad, se edita acá)
        │  rutina diaria — 08:00 (ART), sube SOLO si el repo cambió
        ▼
Drive: 00-NUCLEO/Paquete-Sistema-IA/
├── LEEME - Como usar este paquete en ChatGPT y Gemini.md
├── INSTRUCCIONES - Proyecto ChatGPT Work.md   ← setup paso a paso + texto para el Proyecto
├── PAQUETE-SISTEMA - 2026-07-20.md            ← primero, generado manualmente
└── PAQUETE-SISTEMA - <fecha>.md               ← uno nuevo por cada día CON cambios (nunca se borra el anterior)
        │
        ▼
ChatGPT (conector Drive o subida a un Proyecto) · Gemini (Workspace) · cualquier IA
```

- Carpeta Drive: `Paquete-Sistema-IA` (id `1NlrylkFD5R-ksnOXjByc9eHlmSUCdiAY`, dentro de `00-NUCLEO`).
- Rutina programada: **"Espejo Paquete-Sistema-IA (diario)"** (`trig_01H2PZVqtpK6a6o1x7bNAEFz`), todos los días 08:00 hora argentina, ligada a la sesión remota de Claude con conector de Drive. Control de cambios por hash de commit: si el repo no cambió desde el último paquete, no sube nada.
- Regla de dirección única: **repo → Drive**. El espejo es de solo lectura para las otras IA; si ChatGPT/Gemini generan una decisión o mejora, se le propone a Julio y se aplica en el repo, nunca al revés. Así no hay dos fuentes de verdad.
- Lo que ChatGPT/Gemini produzcan como *trabajo* (documentos, borradores) se guarda en Drive como siempre — el espejo solo reemplaza el *contexto*.

## Instrucción para pegar en ChatGPT (Proyecto o chat)

> "Antes de responder, buscá en mi Google Drive la carpeta 'Paquete-Sistema-IA' y leé el archivo
> PAQUETE-SISTEMA más reciente. Es el contexto completo de mi administración de consorcios.
> Respetá sus reglas de oro: nunca enviar nada hacia afuera sin mi aprobación, nunca borrar,
> no exponer datos de 'No compartido'."

## Mantenimiento

- Si la rutina falla (p. ej. la sesión pierde el conector de Drive), recrearla desde la interfaz de
  Rutinas de claude.ai adjuntando el conector de Google Drive, con el mismo prompt.
- Al dar de baja o alta un consorcio, o cambiar una regla: editar el repo → el lunes siguiente el
  espejo se actualiza solo (o pedirle a Claude que lo regenere en el momento).

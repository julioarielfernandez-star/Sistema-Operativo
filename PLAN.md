# Plan maestro — Sistema Operativo personal y de administración

Este documento define cómo armar un sistema único para gestionar la administración de consorcios, los proyectos personales y las automatizaciones, operable por vos, tus empleados, colaboradores y socios, usando varias IA (Claude, ChatGPT, Gemini).

---

## 1. Qué ya tenés y qué sirve

Lo más valioso que construiste hasta ahora **no es código**: es tu entorno de Claude ya configurado.

**Skills ya creadas (procedimientos automatizados):**

| Skill | Qué hace |
|---|---|
| `organizar-consorcios` | Clasifica documentos sueltos de Drive en la carpeta de cada consorcio |
| `redaccion-acta-de-asamblea` | Redacta actas a partir de audio o transcripción |
| `redaccion-convocatoria-de-asamblea` | Genera convocatorias (carta formal + versión WhatsApp) |
| `redaccion-de-comunicaciones` | Redacta comunicaciones a propietarios |
| `tablero-vencimientos-sheets` | Dashboard de vencimientos en vivo desde Google Sheets |
| `morning` | Brief matinal del día |

**Conectores ya activos:** Gmail, Google Calendar, Google Drive, Slack y Plaud (grabadora/transcripciones).

**Este repositorio (`Sistema-Operativo`):** hoy vacío, pero es el lugar correcto para centralizar la documentación del sistema: procedimientos, skills versionadas, estructura de carpetas, reglas de trabajo.

Conclusión: ya tenés el 40% del sistema hecho. Lo que falta no es más tecnología, es **estructura y documentación** para que deje de depender de tu cabeza.

---

## 2. Arquitectura recomendada

Principio central: **las IA no comparten cerebro entre sí; comparten tus datos y tus procedimientos.**

```
        DATOS (fuente de verdad única)
        Google Drive + Google Sheets + Gmail + Calendar
                        │
        ────────────────┼────────────────
        │               │               │
     Claude          ChatGPT         Gemini
   (operador        (consultas      (integrado a
    principal:       puntuales,      Workspace:
    skills +         segunda         resúmenes en
    conectores)      opinión)        Gmail/Docs)
                        │
        PROCEDIMIENTOS (este repo + skills)
        Cómo se hace cada cosa, escrito una sola vez
```

- **Nube, sí.** Ya estás en la nube (Drive + Claude web/Cowork). No conviene nada local: se pierde, no se comparte, no lo operan otros.
- **Cowork, sí.** Es la interfaz correcta para vos y para empleados no técnicos: chat + conectores + skills, sin terminal.
- **Claude = operador principal**, porque es el único de los tres donde ya invertiste en skills y conectores. ChatGPT y Gemini se usan como herramientas complementarias, no como sistemas paralelos. Si un día querés cambiar de IA, los datos (Drive) y los procedimientos (este repo) siguen siendo tuyos: eso es lo que te hace independiente del proveedor.

---

## 3. Paso a paso

### Fase 1 — Ordenar los datos (semana 1–2)
1. Definir la estructura estándar de carpetas en Drive: `Administracion/<Consorcio>/...` con subcarpetas iguales en todos (Actas, Liquidaciones, Proveedores, Legales, Comunicaciones).
2. Correr `organizar-consorcios` hasta dejar la raíz de Drive limpia; revisar `_Sin clasificar` una vez por semana.
3. Crear (o consolidar) las planillas maestras en Sheets:
   - **Consorcios**: datos de cada edificio, encargado, consejo, CUIT.
   - **Vencimientos**: todo lo que vence (seguros, matafuegos, ascensores, juicios, cargas sociales) → alimenta `tablero-vencimientos-sheets`.
   - **Proveedores**: contactos, rubro, consorcio.

### Fase 2 — Documentar los procedimientos (semana 2–4)
4. Escribir en este repo un archivo por proceso (`procesos/liquidacion-mensual.md`, `procesos/asamblea.md`, `procesos/alta-consorcio.md`...): qué se hace, en qué orden, con qué skill, quién aprueba.
5. Convertir en skill todo proceso que se repita más de 2 veces por mes y hoy hagas "a mano" con la IA (ej.: respuesta a reclamos de propietarios, resumen semanal de mails por consorcio, control de liquidaciones).
6. Versionar las skills en este repo (carpeta `skills/`), así no viven solo en tu cuenta.

### Fase 3 — Sumar al equipo (mes 2)
7. Pasar a un plan **Claude Team**: cada empleado con su cuenta, skills compartidas a nivel organización.
8. Permisos por rol usando los permisos de Drive (no los de la IA): cada empleado ve solo las carpetas de los consorcios que administra; la IA hereda esos permisos vía el conector de cada usuario.
9. Regla operativa: **la IA redacta, un humano aprueba y envía.** Nada sale a un propietario o proveedor sin revisión humana.
10. Capacitación mínima: una sesión mostrando 3 skills; el resto lo aprenden usando.

### Fase 4 — Automatizar lo recurrente (mes 2–3)
11. Brief matinal (`morning`) para vos: agenda + vencimientos + mails importantes.
12. Tareas programadas: revisión semanal del tablero de vencimientos, clasificación automática de documentos nuevos, resumen semanal por consorcio para socios.
13. Plaud → acta: audio de asamblea grabado con Plaud entra directo a `redaccion-acta-de-asamblea` sin pasos manuales.

### Fase 5 — Medir y ampliar (mes 3 en adelante)
14. Una vez por mes: ¿qué tarea manual me comió más tiempo? → esa es la próxima skill.
15. Recién acá evaluar cosas más grandes (portal para propietarios, integración con sistema de expensas) — con los datos ya ordenados, cualquier desarrollo futuro es 10 veces más simple.

---

## 4. Rol de cada IA (para no duplicar esfuerzo)

- **Claude (Cowork/Team):** operación diaria — documentos, actas, comunicaciones, tableros, automatizaciones. Es donde están las skills y los conectores.
- **Gemini:** viene incluido en Google Workspace; útil para resúmenes rápidos dentro de Gmail/Docs/Sheets sin salir de la app.
- **ChatGPT:** segunda opinión en temas puntuales (legales, redacción sensible) o herramientas específicas que Claude no tenga. No cargarle procedimientos: se duplica el mantenimiento.

Regla: **un solo lugar para los procedimientos (este repo) y un solo operador principal (Claude).** Las demás IA son satélites.

---

## 5. Reglas de oro

1. Fuente de verdad única: si no está en Drive/Sheets, no existe.
2. Todo proceso repetido 2+ veces se documenta; documentado 2+ veces, se vuelve skill.
3. La IA propone, el humano aprueba (todo lo que sale hacia afuera).
4. Los permisos se manejan en Drive, no en la IA.
5. Los datos y procedimientos son tuyos e independientes de cualquier proveedor de IA.

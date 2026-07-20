# Estructura de Google Drive — Mapa del sistema de archivos

> Relevado el 2026-07-19 leyendo el Drive real + `Administracion/CLAUDE.md` (cerebro del módulo, 2026-06-16) + `00-NUCLEO/MAESTRO-INDICE.md` y `Traspaso-Sistema.md` (2026-07-11).

## Los 3 módulos (raíz de Mi unidad)

```
Mi unidad/
├── 00-NUCLEO/          → contexto compartido, metodología, motor de tareas
├── Administracion/     → módulo "01-ADMINISTRACION" (NO renombrar: en producción)
├── 02-PROYECTOS/       → otros negocios (Empresores, Rama-Servicios, Rama-Tech)
└── Ordenar/            → bandeja de entrada general (2026-07)
```

**Orden de lectura para cualquier asistente:** `00-NUCLEO/Memoria.md` → `MAESTRO-INDICE.md` → índice del módulo → ficha concreta.

## 00-NUCLEO — metodología y tareas

| Archivo | Función |
|---|---|
| `Memoria.md` | Identidad, socios, visión, bancos, reglas transversales. Se carga siempre primero |
| `MAESTRO-INDICE.md` | Punto de entrada único; mapea los 3 módulos con alias |
| `Sistema-BRUJULA.md` | Metodología rectora: Covey (Cuadrante II, piedras grandes por rol) + GTD (capturar→aclarar→organizar→revisar→hacer). Plantillas de Revisión Semanal y Arranque Diario |
| `Diario.md` | Bitácora global (desactualizada desde 2026-06-15) |
| `Traspaso-Sistema.md` | Handoff completo del sistema (2026-07-11) |
| `GTD/` | Motor de tareas: `Bandeja.md` → `Tareas.md` → `Archivo.md` + `LEEME-GTD.md`. Captura automática desde Plaud |

**Formato de tarea:** `- [ ] <acción> · @<delegado> · <estado> · vence:AAAA-MM-DD · #<área> · id:T-NNN · src:<origen>`

⚠️ **Problema activo (según Traspaso 2026-07-11):** `Bandeja.md` y `Tareas.md` canónicos están vacíos; los datos reales (42 tareas T-001…T-042) viven en copias de conflicto de Drive `Tareas (2).md` y `Bandeja (1).md`. Sistema sin tocar desde 2026-06-21. Primer arreglo pendiente: consolidar canónicos con aprobación de Julio.

## Administracion — módulo de consorcios

### Convenciones

- `NN. Nombre` → un consorcio. Adentro:
  - `NN. Compartido` → documentación que SÍ se comparte con propietarios
  - `NN. No compartido` → **SENSIBLE** (AFIP, legajos, legales). No sale sin aprobación de Julio
  - `NN. Base Convivencia` → corpus de reglamentos/actas + `BASE-CONVIVENCIA-<COD>.md` sintetizada
  - `NN. Paquete IA` → `NN - INDICE.md` + `NN - PAQUETE IA.md` (autocontenido para subir a cualquier IA) + `LEEME.md`
  - Subcarpetas por tema: `NN. Tema`
- **Nombre de archivo:** `NN - Tema - AAAA-MM-DD - Descripción.ext`
- `00. Administracion` → interno (empleados, marca, legales, `00. Equipo/Panel del Equipo.md` y `Matriz de Responsabilidades.md`, `00. Vencimientos/`)
- `GESTIONAR 2026` → trabajo del año en curso (liquidaciones, actas, DDJJ, F.931)
- `_organizador` → scripts de organización + logs + informes
- `_Sin clasificar` → lo que el organizador no pudo identificar
- `Documentos Escaneados` / `Documentos Ordenar` / `.Bandeja de entrada` → bandejas de entrada
- `Archivos <Nombre>` → carpetas históricas por persona (Ariel, Paola, Laura, Martin, Ana, Nacho, Matias, Pamela, Lujan, Juan Ignacio, Guillermo Pantelakis, Hernan) y por tema (Legales, Abogados, Seguros, Conciliaciones, Comunicaciones, Convivencia, Gestión, Asambleas, Consorcios, Tecnicos)
- `Procedimientos` → SOPs escritos (mantenimiento correctivo, control de abonos, ascensores, liquidaciones, template nuevo consorcio, checklist interno)

### Lista maestra de consorcios (fuente: `_organizador/organizar_real.py`)

| Cód | Carpeta | CUIT | Dirección / alias |
|-----|---------|------|-------------------|
| 21 | 21. Mitre 1699 | 30562137137 | Mitre 1699 |
| 24 | 24. Supisiche 11 | 30634503745 | Supisiche 11 |
| 27 | 27. Ameghino 1037 | 30586889644 | Ameghino 1037 |
| 29 | 29. 12 de octubre 53 | 30559970278 | 12 de Octubre 53 |
| 31 | 31. Mitre 2414 | 30551725363 | Mitre 2414 / 2412 |
| 32 | 32. Arenales 108 | 30714151955 | Arenales 108 |
| 34 | 34. Mitre 2369 | 30600770515 | Mitre 2369 / 2371 |
| 35 | 35. Mitre 5865 | 30600577666 | Mitre 5865 |
| 36 | 36. Alsina 281 | 30717128563 | Alsina 281 |
| 37 | 37. Italia 189 | — | Italia 189 (carpeta 2026-06) |
| 103 | 103. General Paz 120 | 30683777400 | General Paz 120 / 122 |
| 201 | 201. Roque Perez 207 | (sin dato) | Roque Pérez 207 / 209 |
| 206 | 206. Estibau 150 | 33719271389 | Estibau 150 |
| 301 | 301. Palmas del Sol | 30697778914 | Pavón 1105/1101, Páez |
| 302 | 302. EBA10 | 30717205673 | Estación Buenos Aires sector 10 |
| 305 | 305. EBA02 | 30716977184 | Estación Buenos Aires sector 2 |
| 306 | 306. EBA09 | 30718181964 | Estación Buenos Aires sector 9 (Torre 13, Miravé 3020) |
| 307 | 307. EBA15 | 30716640996 | Estación Buenos Aires sector 15 (Fangio 3065/3075, Monasterio 720) |
| 330 | 330. PM1751 | (sin dato) | Pedro Mendoza 1751 |
| 350 | 350. GO171 | 30656499695 | Gelly Obes 171 |
| 364 | 364. A518 | 30625047680 | Ameghino 518 |
| 370 | 370. Arenales 277 | 30717061132 | Arenales 277 / Brandsen 1242 |
| 371 | 371. Arenales 269 | 30717061132 | Arenales 269 (comparte CUIT con 370) |

⚠️ Los trackers de vencimientos listan ~31 consorcios/torres, varios sin carpeta propia (Mitre 2012/2636/2648/1829, Alsina 285, Chacabuco 24, Seminario 1314, M. Castro 959, Capello 358, Tucumán 1264, Achával 763, Mitre 616, Colón 152). **Confirmar con Julio cuáles administra hoy.**

### Automatización local (Windows + Python, `_organizador/`)

- `config.py` — rutas centralizadas auto-localizables; chequeo con `Chequeo de salud.cmd`
- `organizar_real.py` — organizador canónico con OCR. Simulación por defecto; `--mover` para ejecutar; `--refile` para reordenar dentro del consorcio. Sensible → `NN. No compartido`. **Nunca borra.** ⚠️ NO usar `organizar_consorcios.py` (desactualizado, crea duplicados)
- `informe_panorama.py` — panorama documental por consorcio (solo lectura)
- `informe_mantenimiento.py` — genera en `00. Administracion/00. Vencimientos/`: informe xlsx + resumen md + `Tablero_mantenimiento.html` (semáforo por días). Atajo: `Actualizar tablero.cmd`. Refresco MANUAL cuando Paola/Martín actualizan la planilla
- `paquetes/generar_paquetes.py` — Paquetes IA por consorcio (`--todos`/`--consorcio NN`/`--zip`). Tarea Programada de Windows "Paquetes Consorcios (semanal)", lunes 8:00. Reporte: `paquetes/00 - CAMBIOS.md`
- `convivencia/` — `PROTOCOLO-CONVIVENCIA.md`, `construir_corpus.py --todos`, `ocr_pendientes.py --todos`. EBA15 (307) tiene base sintetizada completa + plugin compartible

### Fuentes de datos clave (`Archivos Gestión/`)

- **Vencimientos de mantenimiento/seguridad:** `Abonos Control de vtos - actualizada x Paola 05052025 - Martin.xlsx`, pestaña "Copia de Control OK", encabezado fila 3. Columna `Vto` = FRECUENCIA (`ANUAL 8`, `SEMESTRAL 3-9`, `TRIMESTRAL 1-4-7-10`…). **Estado anual por COLOR de celda:** verde=hecho · amarillo=pendiente · rojo=revisar · azul=falta 2º vto · violeta=vencido urgente · blanco=sin gestionar
- **Vencimientos de pagos/impuestos:** `Vtos. de servicios y abonos por consorcios 2026-.xlsx` (cuenta proveedores@); naranja=cargada, verde=pagada. Tablero propio pendiente
- **Proveedores:** `Reporte Rubro proveedores por consorcio.xlsx`
- Tareas críticas legales/seguridad: oblea ascensores, oblea instalaciones fijas, hidrantes, extintores, detector de humo, fachada Ley 257

### Naturaleza jurídica (regla de convivencia)

Los PRO.CRE.AR (EBA02/09/10/15 y prob. Palmas del Sol) son **fideicomiso / consorcio de hecho** → multas = herramienta de gestión, no título ejecutivo (intimación → mediación → justicia, art. 2069 CCCN). Los de **PH constituido** sí aplican sanciones por reglamento. Confirmar leyendo el reglamento de cada consorcio.

## 02-PROYECTOS — otros negocios

- `Indice-Proyectos.md`, `_PLANTILLA-PROYECTO.md`, `_INDICE.md`
- `Negocios/`: Empresores, Rama-Servicios, Rama-Tech
- `Transferencia de Proyecto - Portafolio de Negocios - 2026-07-11.md`

## Cuentas Google del ecosistema

| Cuenta | Uso |
|---|---|
| julioarielfernandez@gmail.com | Titular |
| soporte.julioarielfernandez@gmail.com | Comprobantes y liquidaciones |
| proveedores.julioarielfernandez@gmail.com | Proveedores y vencimientos de pagos |
| consorcios.jaf@gmail.com | Histórico (Archivos Ariel, Facturas honorarios) |
| paolamfranco@gmail.com | Paola — socia |
| andrea.isabel.fernandez@gmail.com | Conciliaciones |

## Reglas de trabajo (de `CLAUDE.md` y `Memoria.md`)

1. **Nunca borrar**: mover o copiar. Antes de mover en lote: simulación + resumen para aprobación.
2. Nada de `NN. No compartido` sale sin aprobación explícita de Julio.
3. CUIT / datos personales: no van a servicios externos sin permiso.
4. Legales desde Carta Documento en adelante: exclusivos de Ariel y Paola.
5. Respetar convención de nombres `NN - Tema - AAAA-MM-DD - Descripción`.
6. La enumeración recursiva del Drive es lenta: preferir listados acotados por carpeta.
7. Editar contenido desde Claude Code/Cowork; crear y consultar desde claude.ai.

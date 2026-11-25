---
name: indice
description: "Índice de los 16 formularios de Seguridad Social: certificados, declaraciones y convenios internacionales. Úsala cuando el usuario pida un documento de esta materia y no esté claro qué formulario usar: propone el adecuado y lo abre. Requiere Jurisprudenciator."
---

# Seguridad Social: certificados, declaraciones y convenios internacionales: índice de formularios

> Plugin `formularios-seguridad-social-certificados-y-convenios` · 16 formularios · normativa revisada el 25-11-2026.

## Qué es

Para acreditar situaciones ante la Seguridad Social: certificados de periodos de actividad (deportistas, ministros de culto…), declaraciones responsables, acuerdos de jubilación parcial y fichas de los convenios bilaterales e internacionales de Seguridad Social.

## Cómo se usa

Cuéntale a Claude qué documento necesitas y para qué caso. Esta skill busca en la lista de abajo el formulario que mejor encaja (por tipo de documento y por su nombre) y lo abre. Si hay dos o tres que encajan, te los propone para que elijas.

Ejemplos de petición:

- «Certificado del club para acreditar los periodos como deportista profesional»
- «Declaración responsable de exención de cotización»
- «Certificado de legislación aplicable para un trabajador desplazado»

## Instrucciones para Claude

### Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

### Cómo elegir

Busca por tipo de documento y por nombre. Cada formulario es una skill de este plugin (`/formularios-seguridad-social-certificados-y-convenios:<skill>`). Si dudas entre dos, elige el que mejor encaje con los hechos y dilo; si la petición es ambigua, propón al usuario los dos o tres formularios que mejor encajan y pregúntale cuál quiere. Las reglas del tema están en `marco.md`.

### Cómo usar el formulario elegido

Invoca su skill. Si esa skill no aparece en tu lista de skills disponibles (puede pasar cuando hay muchas skills instaladas), lee directamente su fichero `SKILL.md`: está en la carpeta hermana de esta (`../<skill>/SKILL.md`). Síguelo igual que si la hubieras invocado: el formulario que se rellena está en `../<skill>/assets/formulario.md` y la guía del tema es el `marco.md` de esta carpeta.

### Contratos, pactos y cláusulas (1)

| Código | Formulario | Skill |
|---|---|---|
| SS-058 | Acuerdo de jubilación parcial entre empresario y persona trabajadora | `acuerdo-jubilacion-parcial-entre-empresario-persona-ss-058` |

### Estatutos, actas, certificaciones y escrituras (3)

| Código | Formulario | Skill |
|---|---|---|
| SS-047 | Certificación del club deportivo sobre los periodos de actividad como deportista profesional | `certificacion-club-deportivo-sobre-periodos-actividad-ss-047` |
| SS-048 | Certificado de condición de ministro de culto evangélico y tiempo de ejercicio en España | `certificado-condicion-ministro-culto-evangelico-tiempo-ss-048` |
| SS-049 | Certificado de la federación deportiva sobre los periodos de actividad como deportista profesional | `certificado-federacion-deportiva-sobre-periodos-ss-049` |

### Comunicaciones, requerimientos y cartas (7)

| Código | Formulario | Skill |
|---|---|---|
| SS-051 | Comunicación al INSS de la imposibilidad de embargar el salario | `comunicacion-inss-imposibilidad-embargar-salario-ss-051` |
| SS-052 | Declaración responsable de exención de cotización por ERTE y Mecanismo RED | `declaracion-responsable-exencion-cotizacion-erte-ss-052` |
| SS-053 | Declaración jurada del autónomo y su familiar sobre la contratación del familiar por cuenta ajena | `declaracion-jurada-autonomo-familiar-sobre-contratacion-ss-053` |
| SS-054 | Declaración responsable sobre la cuota de reserva de empleo para personas con discapacidad | `declaracion-responsable-sobre-cuota-reserva-empleo-ss-054` |
| SS-056 | Comunicación de la persona trabajadora a la empresa de su ausencia o reducción de jornada | `comunicacion-persona-trabajadora-empresa-ausencia-ss-056` |
| SS-057 | Solicitud de certificado de silencio administrativo tras recurso de alzada contra acta de infracción | `solicitud-certificado-silencio-administrativo-tras-ss-057` |
| SS-059 | Denuncia ante la Inspección de Trabajo de un representante de los trabajadores y sindical | `denuncia-ante-inspeccion-trabajo-representante-ss-059` |

### Escritos de trámite y otros (5)

| Código | Formulario | Skill |
|---|---|---|
| SS-050 | Formularios del convenio de Seguridad Social con las islas de Man y Jersey (Reino Unido) | `formularios-convenio-seguridad-social-islas-man-jersey-ss-050` |
| SS-055 | Relación de convenios bilaterales de Seguridad Social suscritos por España con otros países | `relacion-convenios-bilaterales-seguridad-social-ss-055` |
| SS-060 | Formularios del convenio de Seguridad Social con Suiza para nacionales de terceros países | `formularios-convenio-seguridad-social-suiza-nacionales-ss-060` |
| SS-061 | Formularios del convenio de Seguridad Social con Turquía para el desplazamiento de trabajadores | `formularios-convenio-seguridad-social-turquia-ss-061` |
| SS-062 | Formularios para trabajadores desplazados a embajadas y consulados de países sin convenio bilateral | `formularios-trabajadores-desplazados-embajadas-ss-062` |

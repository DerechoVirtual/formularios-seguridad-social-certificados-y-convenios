# Seguridad Social: certificados, declaraciones y convenios internacionales

> Plugin de Claude Code `formularios-seguridad-social-certificados-y-convenios` · **16 formularios** · Seguridad Social · normativa revisada el 25-11-2026 · requiere Jurisprudenciator

## Para qué sirve

Para acreditar situaciones ante la Seguridad Social: certificados de periodos de actividad (deportistas, ministros de culto…), declaraciones responsables, acuerdos de jubilación parcial y fichas de los convenios bilaterales e internacionales de Seguridad Social.

Cada formulario es una skill: Claude lo rellena contigo paso a paso y te entrega el documento en Word, con las normas comprobadas en el BOE. Cada skill explica en su `SKILL.md` qué es el formulario, para qué sirve, cómo se usa, qué datos necesita y qué avisos normativos lleva; el formulario seco, listo para rellenar, está en `assets/formulario.md` dentro de la carpeta de la skill.

## Qué puedes hacer con él

Estos son los tipos de documento que trae, con algunos ejemplos (la lista completa de los 16 está al final):

- **Contratos, pactos y cláusulas** (1). Por ejemplo: Acuerdo de jubilación parcial entre empresario y persona trabajadora.
- **Estatutos, actas, certificaciones y escrituras** (3). Por ejemplo: Certificación del club deportivo sobre los periodos de actividad como deportista profesional; Certificado de condición de ministro de culto evangélico y tiempo de ejercicio en España; Certificado de la federación deportiva sobre los periodos de actividad como deportista profesional.
- **Comunicaciones, requerimientos y cartas** (7). Por ejemplo: Comunicación al INSS de la imposibilidad de embargar el salario; Declaración responsable de exención de cotización por ERTE y Mecanismo RED; Declaración jurada del autónomo y su familiar sobre la contratación del familiar por cuenta ajena.
- **Escritos de trámite y otros** (5). Por ejemplo: Formularios del convenio de Seguridad Social con las islas de Man y Jersey (Reino Unido); Relación de convenios bilaterales de Seguridad Social suscritos por España con otros países; Formularios del convenio de Seguridad Social con Suiza para nacionales de terceros países.

## Cómo se usa

1. **Pídelo con tus palabras.** Cuéntale a Claude qué documento necesitas y para qué caso; él elige el formulario. Por ejemplo:
   - «Certificado del club para acreditar los periodos como deportista profesional»
   - «Declaración responsable de exención de cotización»
   - «Certificado de legislación aplicable para un trabajador desplazado»
2. **Si no da con el formulario**, empieza por el índice del plugin: escribe `/formularios-seguridad-social-certificados-y-convenios:indice` y cuéntale lo que necesitas. Te propondrá el formulario que mejor encaja (o dos o tres para que elijas).
3. **Si ya sabes cuál quieres**, llámalo por su nombre de skill, por ejemplo `/formularios-seguridad-social-certificados-y-convenios:certificacion-club-deportivo-sobre-periodos-actividad-ss-047`. Los nombres están en la lista de formularios de abajo.

## Qué hace Claude cuando usas un formulario

1. Comprueba que Jurisprudenciator está conectado. Si no lo está, se para y te dice cómo conectarlo: no redacta nada sin él. Todos los datos jurídicos del documento (artículos vigentes, sentencias con su ECLI, datos registrales) salen de Jurisprudenciator; nunca de memoria.
2. Te pide en una sola tanda los datos del caso (partes, órgano, fechas, importes…). Lo que no sepas queda como hueco visible.
3. Resuelve contigo las opciones que el formulario deja abiertas y decide qué párrafos opcionales entran según los hechos.
4. Aplica las notas de actualización de la revisión del 25-11-2026 (reformas legales, órganos judiciales de la LO 1/2025, plazos).
5. Comprueba en el BOE, con Jurisprudenciator, cada norma que cita el documento; si alguna ha cambiado, usa la redacción vigente y te lo dice.
6. Te entrega el documento en Word **tal cual es el formulario**: empieza por su primera línea, sin títulos, notas ni explicaciones añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. En el chat te dice lo que queda pendiente y, si es un escrito, el plazo y ante quién se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.

## Antes de empezar

- **Dónde funciona:** en Claude Code y en Claude (web, escritorio y Cowork). Se instala desde este repositorio de GitHub o subiendo el ZIP del plugin.
- **Jurisprudenciator es imprescindible:** el plugin trae el conector y cada skill trabaja siempre con él. Sin una cuenta de Jurisprudenciator conectada, las skills se paran y no redactan nada. La primera vez hay que iniciar sesión (en Claude Code, con `/mcp`; o con tu URL personal: https://jurisprudenciator.lexiaipro.org/instalacion). Si ya tienes Jurisprudenciator conectado en Claude, las skills usan ese.
- **Espacio que ocupa:** unos 1.083 tokens en cada conversación mientras esté activado, porque Claude lleva en memoria la descripción de cada skill. Activa solo los plugins que vayas a usar; los demás puedes desactivarlos sin desinstalarlos (`claude plugin disable formularios-seguridad-social-certificados-y-convenios@formularios-seguridad-social-certificados-y-convenios`).

## Instalación

En Claude Code, añade el catálogo (solo la primera vez) e instala el plugin:

```
/plugin marketplace add DerechoVirtual/formularios-seguridad-social-certificados-y-convenios
/plugin install formularios-seguridad-social-certificados-y-convenios@formularios-seguridad-social-certificados-y-convenios
```

En Claude (web, escritorio o Cowork): **Personalizar → Plugins → Añadir marketplace** con la dirección `https://github.com/DerechoVirtual/formularios-seguridad-social-certificados-y-convenios`, o sube el ZIP del plugin ([descargar ZIP](https://github.com/DerechoVirtual/formularios-seguridad-social-certificados-y-convenios/releases/latest/download/formularios-seguridad-social-certificados-y-convenios.zip)).

Para comprobar que está instalado: `claude plugin list`.

## Lista completa de formularios (16)

| Código | Formulario | Skill |
|---|---|---|
| SS-047 | Certificación del club deportivo sobre los periodos de actividad como deportista profesional | `certificacion-club-deportivo-sobre-periodos-actividad-ss-047` |
| SS-048 | Certificado de condición de ministro de culto evangélico y tiempo de ejercicio en España | `certificado-condicion-ministro-culto-evangelico-tiempo-ss-048` |
| SS-049 | Certificado de la federación deportiva sobre los periodos de actividad como deportista profesional | `certificado-federacion-deportiva-sobre-periodos-ss-049` |
| SS-050 | Formularios del convenio de Seguridad Social con las islas de Man y Jersey (Reino Unido) | `formularios-convenio-seguridad-social-islas-man-jersey-ss-050` |
| SS-051 | Comunicación al INSS de la imposibilidad de embargar el salario | `comunicacion-inss-imposibilidad-embargar-salario-ss-051` |
| SS-052 | Declaración responsable de exención de cotización por ERTE y Mecanismo RED | `declaracion-responsable-exencion-cotizacion-erte-ss-052` |
| SS-053 | Declaración jurada del autónomo y su familiar sobre la contratación del familiar por cuenta ajena | `declaracion-jurada-autonomo-familiar-sobre-contratacion-ss-053` |
| SS-054 | Declaración responsable sobre la cuota de reserva de empleo para personas con discapacidad | `declaracion-responsable-sobre-cuota-reserva-empleo-ss-054` |
| SS-055 | Relación de convenios bilaterales de Seguridad Social suscritos por España con otros países | `relacion-convenios-bilaterales-seguridad-social-ss-055` |
| SS-056 | Comunicación de la persona trabajadora a la empresa de su ausencia o reducción de jornada | `comunicacion-persona-trabajadora-empresa-ausencia-ss-056` |
| SS-057 | Solicitud de certificado de silencio administrativo tras recurso de alzada contra acta de infracción | `solicitud-certificado-silencio-administrativo-tras-ss-057` |
| SS-058 | Acuerdo de jubilación parcial entre empresario y persona trabajadora | `acuerdo-jubilacion-parcial-entre-empresario-persona-ss-058` |
| SS-059 | Denuncia ante la Inspección de Trabajo de un representante de los trabajadores y sindical | `denuncia-ante-inspeccion-trabajo-representante-ss-059` |
| SS-060 | Formularios del convenio de Seguridad Social con Suiza para nacionales de terceros países | `formularios-convenio-seguridad-social-suiza-nacionales-ss-060` |
| SS-061 | Formularios del convenio de Seguridad Social con Turquía para el desplazamiento de trabajadores | `formularios-convenio-seguridad-social-turquia-ss-061` |
| SS-062 | Formularios para trabajadores desplazados a embajadas y consulados de países sin convenio bilateral | `formularios-trabajadores-desplazados-embajadas-ss-062` |

## Privacidad

Ver `PRIVACY.md`.

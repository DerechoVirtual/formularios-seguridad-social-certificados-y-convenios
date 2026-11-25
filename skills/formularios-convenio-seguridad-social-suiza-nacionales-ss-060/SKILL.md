---
name: formularios-convenio-seguridad-social-suiza-nacionales-ss-060
description: "Formularios del convenio de Seguridad Social con Suiza para nacionales de terceros países. Lo redacta con los datos del caso y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Formularios del convenio de Seguridad Social con Suiza para nacionales de terceros países

> Formulario **SS-060** del plugin **Seguridad Social: certificados, declaraciones y convenios internacionales** (`formularios-seguridad-social-certificados-y-convenios`) · Seguridad Social › Certificados, declaraciones y convenios internacionales · normativa revisada el 25-11-2026.

## Qué es

Ficha práctica sobre los formularios de Seguridad Social del Convenio hispano-suizo aplicables a nacionales de terceros países (no de la Unión Europea): desplazamientos de trabajadores y certificados de legislación aplicable.

Es un modelo de tipo **escritos de trámite y otros**, en su versión revisada y actualizada a la normativa vigente.

## Para qué sirve

Para obtener, en pocos minutos, un borrador completo de «Formularios del convenio de Seguridad Social con Suiza para nacionales de terceros países» adaptado a tu caso y a la normativa vigente, en Word y listo para revisar. Claude no se limita a copiar el modelo: te pide los datos, decide contigo las opciones, redacta las partes que dependen de los hechos y comprueba en el BOE cada norma que cita.

## Cómo se usa

1. **Pídelo con tus palabras**, por ejemplo: «Prepárame el documento “Formularios del convenio de Seguridad Social con Suiza para nacionales de terceros países” para mi caso». También puedes invocarla directamente con `/formularios-seguridad-social-certificados-y-convenios:formularios-convenio-seguridad-social-suiza-nacionales-ss-060`.
2. **Dale los datos del caso** cuando te los pida (abajo tienes la lista para tenerlos a mano). Lo que no sepas queda como hueco visible.
3. **Resuelve las opciones** que te plantee (las marcadas [ELEGIR] y [OPCIONAL] en el modelo).
4. **Recibe el documento en Word, tal cual es el formulario**: empieza por su primera línea (por ejemplo «En [LOCALIDAD], a [FECHA]» o «A LA SECCIÓN…»), sin títulos ni notas añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. Lo pendiente, las normas comprobadas y el plazo te los dice en el chat.

Si no estás seguro de que este sea el formulario que necesitas, usa el índice del plugin: `/formularios-seguridad-social-certificados-y-convenios:indice`.

## Qué contiene esta skill

- `SKILL.md` (este fichero): qué es el formulario, para qué sirve, cómo se usa, los datos que pide, las normas que cita, los avisos de actualización y las instrucciones para Claude.
- `assets/formulario.md`: el formulario seco, tal cual, desde su primera línea hasta la firma, con sus campos [EN MAYÚSCULAS] y sus opciones [ELEGIR…] / [OPCIONAL…]. Es el texto que se rellena; no lleva explicaciones.
- `../indice/marco.md` (en la skill `indice` del plugin): la guía del tema (Seguridad Social: certificados, declaraciones y convenios internacionales) con las normas, órganos y plazos vigentes que Claude lee antes de redactar.

## Datos que conviene tener a mano

- [ ] LOCALIDAD (2 veces)
- [ ] NOMBRE Y APELLIDOS DEL REPRESENTANTE (2 veces)
- [ ] AÑO
- [ ] DENOMINACIÓN SOCIAL
- [ ] DOMICILIO
- [ ] DOMICILIO EN SUIZA
- [ ] DÍA
- [ ] EMPRESA O CENTRO DE TRABAJO DE DESTINO
- [ ] FECHA DE FIN PREVISTA
- [ ] FECHA DE INICIO
- [ ] MES
- [ ] NACIONALIDAD
- [ ] NIF
- [ ] NOMBRE Y APELLIDOS DEL TRABAJADOR
- [ ] Nº DE AFILIACIÓN
- [ ] Nº DE CCC
- [ ] Nº DE DOCUMENTO
- [ ] RELACIÓN DE DOCUMENTOS

## Normas que cita el formulario

- No cita artículos concretos; Claude localizará las normas aplicables con Jurisprudenciator si el documento las necesita.

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

### Avisos de actualización (2) — se aplican en el texto, nunca se copian en el documento

- Al principio del formulario: el original no traía el texto del formulario; modelo redactado de nuevo conforme a la normativa vigente.
- Junto a «…e circulación de personas entre la UE y Suiza y los reglamentos de coordinación.»: comprobar en la sede electrónica de la Seguridad Social el texto vigente del Convenio y sus protocolos, así como los certificados y formularios disponibles; no se consignan códigos de impreso por no poder garantizarse su vigencia.

### Notas de uso del formulario — orientan la redacción, nunca se copian en el documento

FICHA PRÁCTICA

Qué es: para las personas trabajadoras que sean nacionales de terceros países (no de la Unión Europea ni de Suiza) y se desplacen entre España y Suiza, la coordinación de Seguridad Social se rige por el Convenio bilateral de Seguridad Social entre España y Suiza y sus instrumentos complementarios. La situación de los nacionales de Estados miembros de la UE se rige, en cambio, por el Acuerdo sobre libre circulación de personas entre la UE y Suiza y los reglamentos de coordinación.

Qué se solicita habitualmente: certificado de legislación aplicable (certificado de desplazamiento), que acredita que el trabajador desplazado continúa sujeto a la legislación de Seguridad Social española durante el periodo de desplazamiento, con exención de cotizar en Suiza.

Quién lo solicita: la empresa que desplaza al trabajador, o el propio trabajador por cuenta propia, ante la Tesorería General de la Seguridad Social (Dirección Provincial o Administración de la TGSS de su domicilio o de la cuenta de cotización), a través de la sede electrónica o del sistema RED.

Datos que se piden: datos de la empresa (denominación, NIF, código de cuenta de cotización, domicilio); datos del trabajador (nombre, DNI/NIE o pasaporte, nacionalidad, número de afiliación); datos de la empresa o centro de trabajo de destino en Suiza; fecha de inicio y duración prevista del desplazamiento; confirmación de que existe vinculación laboral con la empresa española durante el desplazamiento.

Documentos que suelen exigirse: justificante de alta en la Seguridad Social española; contrato de trabajo o comunicación del desplazamiento; documentación que acredite el destino en Suiza.

Normativa aplicable: Convenio de Seguridad Social entre España y Suiza; Ley 39/2015, del Procedimiento Administrativo Común.


### Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero `assets/formulario.md` (el formulario que vas a rellenar, en la carpeta de esta skill) y la parte de `../indice/marco.md` que afecte al caso. Limítate a la materia de este formulario: no añadas contenido ajeno a él.
3. Pide los datos de la lista en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez. Lo que el usuario no sepa se queda como hueco visible con su etiqueta (p. ej. [FECHA]).
4. Resuelve cada [ELEGIR …] y cada [OPCIONAL …] según los hechos, y sustituye cualquier indicación entre paréntesis del formulario («(se describirá…)», «(indicar…)») por el contenido que corresponda. Redacta las partes que dependen del caso (hechos, motivos, descripción de bienes).
5. Aplica los avisos de actualización en el lugar que indican. Comprueba con `buscar_articulo` cada norma citada; si alguna ha cambiado, usa la redacción vigente. Si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Antes de entregarlo, pasa `verificar_escrito` con las frases que citan normas o sentencias y corrige lo que señale.
7. **Documento final = el formulario tal cual, rellenado y limpio.**
   - Empieza exactamente por la primera línea de `assets/formulario.md` y sigue su estructura y su orden hasta la firma.
   - No pongas en el documento título, nombre del formulario o de la skill, código, encabezados, «Para qué sirve», leyendas, avisos, notas de uso, comentarios ni explicaciones. Tampoco marcas [ELEGIR…] u [OPCIONAL…]: ya están resueltas.
   - Formato Word (.docx, con la skill de Word disponible): **Times New Roman 11 pt** en todo el documento, **interlineado 1,15**, **texto justificado**, márgenes de 2,5 cm. Los rótulos del formulario (REUNIDOS, CLÁUSULAS, HECHOS, SUPLICO…) en su propia línea y en negrita, sin cambiar su texto.
8. En el chat (nunca dentro del documento): datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator (y, si algún dato sale de internet, cuál y su enlace) y, si es un escrito judicial o administrativo, el plazo y el órgano ante el que se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.

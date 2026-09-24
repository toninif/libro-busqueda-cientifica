# Capítulo 10. Inteligencia artificial para la búsqueda de antecedentes

**En este capítulo vas a aprender:**

- qué tipos de herramientas con inteligencia artificial (IA) existen para buscar y leer literatura académica;
- en qué se diferencia la búsqueda semántica de la búsqueda booleana;
- en qué etapas de la búsqueda la IA ayuda y en cuáles es riesgosa;
- a escribir instrucciones (*prompts*) útiles para tareas de búsqueda;
- a verificar lo que produce una IA y a declarar su uso.

> [!NOTE]
> Este capítulo está actualizado a **septiembre de 2026**. Las herramientas de IA cambian muy rápido: algunas de las que se mencionan pueden cambiar de nombre, de funciones o de condiciones de acceso. Por eso el capítulo se organiza por **tipos de herramientas y usos**, que cambian mucho más lentamente que los productos concretos.

---

## 10.1 Qué cambió

Durante décadas, buscar literatura consistió en elegir términos y combinarlos con operadores (capítulos 4 y 5). Las herramientas con IA agregan tres posibilidades nuevas:

1. **Buscar por significado.** Escribir una pregunta en lenguaje natural ("¿el mindfulness reduce el estrés en universitarios?") y recibir artículos relacionados aunque no usen exactamente esas palabras.
2. **Resumir y extraer.** Obtener un resumen de un artículo, o una tabla con la muestra, el método y los resultados de varios artículos a la vez.
3. **Conversar sobre la búsqueda.** Pedir sinónimos, traducciones, cadenas de búsqueda, críticas a una estrategia o explicaciones de un método estadístico.

Estas posibilidades son reales y útiles. Pero la IA **no reemplaza** a lo que vimos en los capítulos anteriores: lo complementa. Y trae riesgos nuevos que hay que conocer.

## 10.2 Cómo funcionan (lo mínimo que hay que saber)

Los **modelos de lenguaje** (como los que están detrás de ChatGPT, Claude, Gemini o Copilot) generan texto prediciendo qué palabras son más probables a continuación, a partir de lo que aprendieron durante su entrenamiento. Dos consecuencias importantes:

- **Un modelo de lenguaje, por sí solo, no consulta una base de datos.** Si le pedís referencias sin que tenga acceso a una fuente, puede generar referencias **plausibles pero inexistentes** (títulos inventados, autores reales con artículos que nunca escribieron, DOI falsos). Este fenómeno se conoce como **alucinación** y está bien documentado en el caso de las referencias bibliográficas (Walters y Wilder, 2023).
- **Cuando la herramienta está conectada a una fuente** (un índice académico, la web, los PDF que le das), primero recupera documentos y después redacta la respuesta a partir de ellos. Esto se llama **generación aumentada por recuperación** (*RAG*). Reduce mucho las referencias inventadas, pero no las elimina: la herramienta todavía puede **atribuir a un artículo algo que no dice**, resumir mal o elegir fuentes poco representativas.

> [!IMPORTANT]
> **Regla de oro:** toda referencia y todo dato que venga de una IA se verifica **en la fuente original** antes de usarlo. Sin excepciones.

## 10.3 Tipos de herramientas

| Tipo | Qué hace | Ejemplos (septiembre de 2026) |
|---|---|---|
| **Asistentes generales** | Conversan sobre cualquier tema. Con búsqueda web o modos de "investigación profunda" (*deep research*), recorren muchas fuentes y producen un informe con citas. | ChatGPT, Claude, Gemini, Copilot, Perplexity |
| **Buscadores académicos con IA** | Buscan en índices académicos (a menudo Semantic Scholar u OpenAlex) a partir de preguntas en lenguaje natural; resumen y extraen datos de los artículos. | Elicit, Consensus, SciSpace, Undermind, Semantic Scholar |
| **IA dentro de bases tradicionales** | Asistentes integrados en bases de datos de suscripción, que responden preguntas usando solo el contenido de esa base. | Scopus AI, Web of Science Research Assistant, funciones de IA en plataformas como EBSCO o ProQuest |
| **Análisis del contexto de las citas** | Muestran *cómo* se cita un artículo: si otros trabajos lo apoyan, lo discuten o solo lo mencionan. | Scite |
| **Mapas y recomendación** | A partir de artículos semilla, recomiendan trabajos relacionados (capítulo 9). | ResearchRabbit, Litmaps, Connected Papers, Inciteful |
| **Lectura asistida** | Responden preguntas sobre los documentos que les das (PDF, notas), citando el pasaje. | NotebookLM, funciones de "chatear con el PDF" en muchos asistentes y gestores |
| **Cribado asistido** | Aprenden de tus decisiones de inclusión y exclusión y priorizan los registros más probablemente relevantes. | ASReview, funciones de IA de Rayyan y Covidence |

## 10.4 Búsqueda semántica y búsqueda booleana

| | Búsqueda booleana (clásica) | Búsqueda semántica (con IA) |
|---|---|---|
| **Entrada** | Términos y operadores: `(mindful* OR meditat*) AND stress` | Una pregunta: "¿el mindfulness reduce el estrés en universitarios?" |
| **Cómo recupera** | Coincidencia exacta de términos en los campos indicados. | Similitud de significado entre la pregunta y los documentos. |
| **Ventaja** | **Transparente y reproducible**: la misma cadena en la misma base da los mismos resultados; se puede reportar. | Encuentra artículos relevantes que usan otras palabras; no hay que conocer la sintaxis. |
| **Desventaja** | Hay que anticipar todos los sinónimos; curva de aprendizaje. | **Opaca y poco reproducible**: no se sabe exactamente por qué aparece cada resultado; el orden puede cambiar; suele mostrar solo una cantidad limitada de resultados. |
| **Cobertura** | La de cada base, conocida y documentada. | La del índice subyacente, a menudo con menor cobertura de revistas en español y de acceso cerrado. |
| **Uso ideal** | Búsqueda principal y reportable, revisiones sistemáticas. | Exploración inicial, descubrimiento de términos y artículos semilla, verificación complementaria. |

> [!TIP]
> Una combinación muy productiva: usar la búsqueda semántica **al principio**, para descubrir artículos y términos, y **al final**, para comprobar si la cadena booleana se perdió algo importante. Si la IA encuentra un estudio relevante que tu cadena no recuperó, analizá por qué y corregí la cadena.

## 10.5 La IA en cada etapa de la búsqueda

| Etapa | Usos recomendables | Riesgos | Cómo mitigarlos |
|---|---|---|---|
| Formular la pregunta (cap. 2 y 7) | Pedir que critique tu pregunta; que la reformule en PICO u otro formato; que proponga preguntas más acotadas. | Que termines investigando la pregunta de la IA y no la tuya. | Usala para discutir, no para decidir. |
| Identificar términos (cap. 4 y 6) | Generar sinónimos, variantes, siglas y traducciones en español, inglés y portugués; sugerir descriptores. | Descriptores inexistentes; traducciones literales; términos que nadie usa. | Verificar cada descriptor en el tesauro; comprobar cada término en una base. |
| Construir la cadena (cap. 5) | Traducir una cadena de una base a otra; detectar errores de paréntesis y operadores; proponer bloques. | Sintaxis incorrecta o desactualizada; campos que no existen. | Ejecutar la cadena en la base y revisar resultados; comparar con la ayuda oficial. |
| Explorar la literatura | Buscadores académicos con IA para encontrar artículos semilla y revisiones. | Sesgo hacia literatura en inglés y de acceso abierto; resultados no reproducibles. | Complementar con búsqueda booleana y bases regionales. |
| Cribar (cap. 8) | Priorizar registros con herramientas de aprendizaje activo (ASReview); segunda opinión sobre casos dudosos. | Exclusión de estudios relevantes sin revisión humana. | Decisión final siempre humana; reportar la herramienta y el criterio de detención. |
| Leer y extraer datos | Resumir; ubicar en el texto la muestra, el método o un resultado; traducir un artículo en otro idioma. | Resúmenes incorrectos; datos atribuidos al artículo equivocado; matices perdidos. | Verificar cada dato extraído en el texto original; leer siempre el método y los resultados. |
| Evaluar fuentes (cap. 11) | Ver cómo fue citado un artículo (Scite); detectar retracciones. | Confiar en una etiqueta automática sin leer. | Leer los pasajes de citas que la herramienta muestra. |
| Escribir (cap. 12) | Revisar claridad y ortografía; sugerir estructura; detectar párrafos que solo enumeran estudios. | Plagio, referencias inventadas, pérdida de la voz propia, incumplimiento de normas institucionales. | Escribir vos; citar solo lo que leíste; declarar el uso. |

## 10.6 Instrucciones (*prompts*) útiles

Una buena instrucción da **contexto**, pide una **tarea concreta**, fija un **formato** de respuesta y pide que la IA **señale sus dudas**. Algunos modelos para adaptar:

**Generar términos bilingües**

```text
Estoy preparando una búsqueda bibliográfica para una tesina de Psicología.
Pregunta: ¿los programas de mindfulness reducen el estrés académico en
estudiantes universitarios?

Para cada concepto (población, intervención, resultado) dame una tabla con:
- sinónimos y variantes en español (incluí variantes regionales),
- equivalentes en inglés y en portugués,
- posibles descriptores MeSH, DeCS y del APA Thesaurus.

Marcá con (?) cualquier descriptor del que no estés seguro de que exista
con ese nombre exacto. No inventes términos.
```

**Traducir una cadena entre bases**

```text
Tengo esta estrategia de búsqueda para PubMed:
[pegar la cadena]

Adaptala a la sintaxis de Scopus (TITLE-ABS-KEY) y de Web of Science (TS=).
Explicá cada cambio que hagas. Como Scopus y Web of Science no usan MeSH,
indicá qué palabras clave deberían reemplazar a cada descriptor.
```

**Revisar una cadena**

```text
Revisá esta cadena de búsqueda como lo haría un bibliotecario usando la
lista de control PRESS: [pegar la cadena]

Señalá errores de operadores o paréntesis, sinónimos que falten,
truncamientos demasiado cortos o largos y términos que puedan traer
mucho ruido. No reescribas la cadena entera: listá los problemas.
```

**Extraer datos de un artículo que tenés abierto**

```text
A partir del artículo adjunto, completá esta tabla: autores y año, país,
diseño, tamaño y características de la muestra, intervención, grupo de
comparación, instrumento para medir el estrés, resultado principal.

Para cada dato, citá textualmente la frase del artículo de donde lo
tomaste. Si un dato no figura, escribí "no informado".
```

> [!TIP]
> Pedir que **cite textualmente el pasaje** de donde sale cada dato hace mucho más fácil verificar la respuesta: buscás la frase en el PDF y comprobás que esté y que diga eso.

> [!WARNING]
> **Nunca le pidas a un asistente "diez referencias sobre X"** para copiarlas en tu trabajo. Aunque use búsqueda web, puede mezclar datos de artículos distintos o describir mal lo que dicen. Usá las herramientas de IA para **encontrar** artículos, pero cada referencia que cites tiene que haber pasado por tus manos: localizada en una base o en el sitio de la revista, y leída.

## 10.7 Riesgos que hay que conocer

- **Referencias inventadas o mal atribuidas.** Ver sección 10.2.
- **Cobertura sesgada.** Muchos buscadores con IA se apoyan en índices abiertos donde predominan los artículos en inglés y con resumen disponible. La literatura en español, los libros, las tesis y los informes suelen estar subrepresentados. Una búsqueda solo con IA reproduce, y a veces amplifica, el sesgo de idioma del capítulo 6.
- **Falta de reproducibilidad.** La misma pregunta puede devolver resultados distintos otro día o con otra formulación. Esto la hace inadecuada como búsqueda principal de una revisión sistemática.
- **Opacidad.** No siempre se sabe qué fuentes consultó la herramienta ni con qué criterio ordenó los resultados.
- **Complacencia.** Los asistentes tienden a darle la razón al usuario. Si preguntás "¿verdad que el mindfulness reduce el estrés?", es más probable que encuentres confirmaciones. Formulá preguntas neutrales y pedí explícitamente la evidencia en contra.
- **Resúmenes que aplanan los matices.** Un resumen automático puede omitir limitaciones, tamaños de efecto pequeños o resultados no significativos.
- **Privacidad y confidencialidad.** No subas datos personales de participantes, manuscritos inéditos de otras personas ni información confidencial. Revisá las condiciones de uso de cada herramienta y las políticas de tu institución.
- **Derechos de autor.** Subir PDFs de suscripción a servicios externos puede violar las licencias de tu biblioteca. Consultá antes.
- **Aprendizaje.** Si la IA hace todo el trabajo, no desarrollás el criterio para juzgar la literatura, que es justamente lo que se evalúa en un trabajo académico.

## 10.8 Protocolo de verificación

Antes de usar algo que produjo una herramienta de IA, respondé:

- [ ] ¿La referencia **existe**? La busqué por título o DOI en una base de datos, en Google Académico o en el sitio de la revista.
- [ ] ¿Los **metadatos son correctos**? Autores, año, título, revista, volumen, páginas y DOI coinciden con la fuente.
- [ ] ¿El artículo **dice lo que la IA dice que dice**? Lo verifiqué en el resumen y, para datos concretos, en el texto completo.
- [ ] ¿El artículo **fue retractado**? (capítulo 11).
- [ ] ¿Los **descriptores** sugeridos existen en el tesauro con ese nombre exacto?
- [ ] ¿La **cadena** funciona en la base? La ejecuté, revisé los resultados y la registré en la bitácora.
- [ ] ¿Busqué también en **español** y en **bases regionales**, o solo usé lo que me dio la IA?
- [ ] ¿Anoté **qué herramienta, cuándo y para qué** la usé?

## 10.9 La IA en revisiones sistemáticas

En 2025, cuatro de las principales organizaciones dedicadas a la síntesis de evidencia —Cochrane, la Campbell Collaboration, JBI y la Collaboration for Environmental Evidence— publicaron una declaración conjunta sobre el uso de IA en revisiones, en la que adhieren a las recomendaciones **RAISE** (*Responsible use of AI in evidence SynthEsis*) (Flemyng et al., 2025). Sus ideas centrales, que también sirven para un trabajo estudiantil:

- **Quien hace la revisión es responsable** de ella, incluida la decisión de usar IA.
- La IA puede **asistir** en tareas como el diseño de la búsqueda, la priorización del cribado o la extracción de datos, **siempre con supervisión humana** y solo si no compromete el rigor metodológico.
- Las herramientas deben estar **evaluadas** para la tarea en la que se usan, y su uso debe **reportarse** con detalle (qué herramienta, qué versión, para qué, cómo se verificó).
- La búsqueda principal sigue apoyándose en **estrategias booleanas reproducibles** en bases de datos documentadas.
- En el cribado con aprendizaje activo (como ASReview), hay que definir y reportar **cuándo se detuvo** la revisión manual y por qué (por ejemplo, después de una cantidad determinada de registros irrelevantes consecutivos).

## 10.10 Declarar el uso de IA

Cada vez más revistas, universidades y cátedras piden que se declare el uso de IA. Primero, **consultá la política de tu institución y de tu cátedra**: algunas lo permiten con declaración, otras lo restringen para ciertas tareas.

Una declaración útil dice **qué herramienta**, **para qué tarea** y **cómo se verificó**. Ejemplo para la sección de método:

> *Se utilizó un asistente de inteligencia artificial generativa (nombre de la herramienta, versión, fecha de uso) para generar una lista inicial de sinónimos en español, inglés y portugués y para adaptar la sintaxis de la estrategia de búsqueda de PubMed a Scopus y Web of Science. Todos los descriptores se verificaron en los tesauros MeSH y DeCS, y todas las estrategias se ejecutaron y revisaron manualmente. No se utilizó IA para seleccionar estudios ni para redactar el texto.*

Para citar una herramienta de IA en formato APA, la American Psychological Association publicó lineamientos en su blog de estilo (McAdoo, 2023).

---

## 10.11 Clásico y con IA: un balance

| | Herramientas clásicas | Herramientas con IA |
|---|---|---|
| Mejor para | Búsqueda principal, reproducible y reportable | Exploración, descubrimiento de términos y artículos, lectura asistida |
| Transparencia | Alta | Variable, a menudo baja |
| Cobertura en español | Buena en bases regionales | En general, limitada |
| Curva de aprendizaje | Mayor (sintaxis) | Menor (lenguaje natural) |
| Riesgo principal | Perder estudios por términos mal elegidos | Información incorrecta presentada con seguridad |

> [!IMPORTANT]
> La IA es un buen **asistente de investigación**, no un buen **investigador**. Te puede ahorrar tiempo en tareas mecánicas y ayudarte a pensar, pero la responsabilidad sobre lo que buscás, lo que incluís y lo que afirmás sigue siendo tuya.

---

## Resumen

- Hay distintos tipos de herramientas con IA: asistentes generales, buscadores académicos, IA integrada en bases tradicionales, análisis de citas, mapas, lectura asistida y cribado.
- La búsqueda semántica encuentra lo que usa otras palabras, pero es opaca y poco reproducible; la booleana sigue siendo la base de una búsqueda reportable.
- La IA es especialmente útil para generar términos, traducir cadenas, explorar y leer; es riesgosa para producir referencias y para decidir qué incluir.
- Todo lo que produce una IA se verifica en la fuente original.
- El uso de IA se declara: qué herramienta, para qué y cómo se verificó.

## Actividad

1. Usá el *prompt* de la sección 10.6 para generar términos bilingües para tu pregunta. Verificá cada descriptor sugerido en el tesauro correspondiente. ¿Cuántos existían tal cual?
2. Hacé la misma pregunta en un buscador académico con IA y en tu cadena booleana en Scopus o Web of Science. Compará los diez primeros resultados: ¿cuántos coinciden? ¿Cuántos están en español?
3. Pedile a un asistente general, **sin búsqueda web**, cinco referencias sobre tu tema. Verificá cada una con el protocolo de la sección 10.8. Anotá cuántas existen, cuántas tienen errores y cuántas son inventadas.
4. Redactá la declaración de uso de IA para tu trabajo.

---

[← Capítulo 9](09-busqueda-por-citas.md) · [Índice](../README.md) · [Capítulo 11 →](11-evaluar-fuentes.md)

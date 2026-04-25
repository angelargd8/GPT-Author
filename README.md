# GPT-Author: agente academico para ChatGPT

GPT-Author es una base de conocimiento para configurar un agente de ChatGPT orientado a investigacion academica, especialmente en economia aplicada y campos cercanos. El objetivo es que el agente ayude a pasar de una idea de investigacion a una especificacion clara, plan de literatura, estrategia empirica, borradores, revisiones y preparacion para envio.

Este repositorio no esta pensado como una herramienta local de automatizacion. Esta pensado para cargar sus archivos en el conocimiento de un GPT personalizado o usarlos como instrucciones de referencia dentro de ChatGPT.

Esta basado en el siguiente repositorio: https://github.com/hugosantanna/clo-author

## Que incluye

La carpeta [`knowledge/`](knowledge/) contiene todos los documentos que debe leer el agente:

- `01-chatgpt-readme.md`: mapa general de la base de conocimiento.
- `02-workflow-quick-ref.md`: referencia rapida del flujo de trabajo y comandos.
- `03-domain-profile.md`: perfil disciplinar, journals, metodos, datos y convenciones.
- `04-personal-style-guide.md`: guia para capturar y reutilizar el estilo del usuario.
- `05-journal-profiles.md`: perfiles de journals y criterios de evaluacion.
- `06-rule-workflow.md` a `11-rule-revision.md`: reglas de workflow, contenido, calidad, formato y revision.
- `12-skill-interview-me.md` a `20-skill-review.md`: instrucciones para tareas especificas del agente.

El archivo [`knowledge/UPLOAD_ORDER.txt`](knowledge/UPLOAD_ORDER.txt) indica el orden recomendado para subir los documentos al conocimiento del GPT.

## Como usarlo en ChatGPT

1. Crea un GPT personalizado en ChatGPT.
2. En las instrucciones del GPT, describe su rol como asistente academico para investigacion, escritura y revision.
3. Sube los archivos de [`knowledge/`](knowledge/) siguiendo el orden de [`UPLOAD_ORDER.txt`](knowledge/UPLOAD_ORDER.txt).
4. Ajusta `03-domain-profile.md`, `04-personal-style-guide.md` y `05-journal-profiles.md` a tu campo, journals objetivo y estilo personal.
5. Usa los comandos o nombres de tareas en una conversacion normal con el GPT.

## Comandos principales

| Comando | Comportamiento esperado |
|---|---|
| `/new-project [tema]` | Inicia un proyecto desde una idea. Pregunta campo, objetivo, audiencia, estado del proyecto y datos disponibles. Produce una especificacion inicial con pregunta, motivacion, literatura relevante, datos posibles, estrategia tentativa, estructura del paper y proximos pasos. |
| `/discover interview` | Entrevista al usuario paso a paso para convertir una idea vaga en una especificacion clara. Pregunta por fenomeno, pregunta, mecanismo, datos, metodo, contribucion y riesgos. |
| `/discover lit` | Apoya la revision de literatura. Pide tema, disciplina, tipo de paper y referencias conocidas. Si el GPT tiene navegacion web, debe verificar literatura; si no, debe marcar referencias como pendientes de verificar. |
| `/discover data` | Explora datos posibles. Identifica unidad de analisis, variables necesarias, poblacion, periodo, geografia y restricciones de acceso. |
| `/strategize [pregunta]` | Disena la estrategia del paper. Clasifica el tipo de paper y propone estimando, supuestos, modelo tentativo, amenazas, pruebas de robustez y evidencia necesaria. |
| `/analyze [dataset]` | Planea o interpreta analisis empirico. Si hay datos disponibles, describe estructura, variables, limpieza, descriptivos, modelos y robustez. Si no hay datos, produce un plan de analisis. No debe inventar resultados. |
| `/write [seccion]` | Redacta o revisa una seccion: abstract, introduccion, literatura, teoria, datos, metodos, resultados o conclusion. Primero identifica argumento principal, funcion de parrafos y evidencia disponible. |
| `/review [archivo]` | Actua como revisor critico. Separa problemas de argumento, estructura, evidencia, metodo y estilo. Si es un paper completo, puede dar prioridades o score. |
| `/revise [reporte]` | Convierte comentarios, referee reports o feedback en un plan de revision. Clasifica comentarios como criticos, importantes, menores o de gusto; propone respuesta y cambios al manuscrito. |
| `/talk [formato]` | Convierte el paper en una presentacion. Pregunta formato si no esta claro: seminario, conferencia, job market o lightning. |
| `/submit [journal]` | Hace checklist pre-envio: fit con journal, claridad de contribucion, solidez metodologica, tablas, figuras, bibliografia, replicabilidad y riesgos de rechazo. |
| `/tools [tarea]` | Da checklists e instrucciones operativas. En ChatGPT no debe fingir que ejecuto comandos, compilo archivos o reviso git si no tiene acceso real a esas herramientas. |

## Flujo recomendado

1. **Definir el proyecto:** usa `/new-project` o `/discover interview`.
2. **Mapear literatura:** usa `/discover lit` o `/research-ideation`.
3. **Evaluar datos:** usa `/discover data` o `/data-analysis`.
4. **Disenar la estrategia:** usa `/strategize`.
5. **Redactar:** usa `/write`, `/paper-draft` o una solicitud directa de seccion.
6. **Revisar:** usa `/review` para diagnostico critico.
7. **Responder feedback:** usa `/revise`.
8. **Preparar salida:** usa `/talk` o `/submit`.

## Principios del agente

- **No inventar evidencia.** Si faltan datos, resultados o citas verificadas, debe decirlo claramente.
- **Separar diagnostico de redaccion.** Primero identifica problemas y despues propone cambios.
- **Mantener control humano.** El usuario decide el argumento final, los resultados que se reportan y que se envia.
- **Adaptarse al campo.** El agente debe usar el perfil disciplinar y los journals objetivo para calibrar criterios.
- **Priorizar claridad academica.** Toda sugerencia debe mejorar contribucion, identificacion, evidencia, estructura o estilo.

## Estructura del repositorio

```text
GPT-Author/
|-- README.md
|-- knowledge/
|   |-- UPLOAD_ORDER.txt
|   |-- 01-chatgpt-readme.md
|   |-- 02-workflow-quick-ref.md
|   |-- 03-domain-profile.md
|   |-- ...
|   `-- 20-skill-review.md
```

## Personalizacion

Los tres archivos mas importantes para adaptar el agente son:

- [`knowledge/03-domain-profile.md`](knowledge/03-domain-profile.md): campo, journals, metodos, fuentes de datos y estandares.
- [`knowledge/04-personal-style-guide.md`](knowledge/04-personal-style-guide.md): voz, tono, estructura de parrafos y preferencias de escritura.
- [`knowledge/05-journal-profiles.md`](knowledge/05-journal-profiles.md): journals objetivo, expectativas y criterios de revision.

## Limitaciones

- El agente produce apoyo academico, no reemplaza revision humana.
- La revision simulada no equivale a referees reales.
- Los scores de calidad son heuristicas, no predicciones de publicacion.
- Si ChatGPT no tiene acceso web, toda referencia nueva debe marcarse como pendiente de verificacion.
- Si ChatGPT no tiene acceso a archivos externos o herramientas locales, no debe afirmar que ejecuto comandos o valido outputs.

## Licencia

MIT License. Puedes adaptar esta base de conocimiento a tu propio flujo de investigacion.

---

# GPT-Author: Academic Agent For ChatGPT

GPT-Author is a knowledge base for configuring a ChatGPT agent focused on academic research, especially applied economics and related fields. The goal is to help the agent move from a research idea to a clear specification, literature plan, empirical strategy, drafts, revisions, and submission preparation.

This repository is not intended as a local automation tool. It is designed for uploading its files to a custom GPT's knowledge base or using them as reference instructions inside ChatGPT.

## What It Includes

The [`knowledge/`](knowledge/) folder contains all documents the agent should read:

- `01-chatgpt-readme.md`: general map of the knowledge base.
- `02-workflow-quick-ref.md`: quick reference for the workflow and commands.
- `03-domain-profile.md`: disciplinary profile, journals, methods, data, and conventions.
- `04-personal-style-guide.md`: guide for capturing and reusing the user's writing style.
- `05-journal-profiles.md`: journal profiles and evaluation criteria.
- `06-rule-workflow.md` to `11-rule-revision.md`: rules for workflow, content, quality, formatting, and revision.
- `12-skill-interview-me.md` to `20-skill-review.md`: instructions for specific agent tasks.

[`knowledge/UPLOAD_ORDER.txt`](knowledge/UPLOAD_ORDER.txt) gives the recommended upload order for the GPT knowledge base.

## How To Use It In ChatGPT

1. Create a custom GPT in ChatGPT.
2. In the GPT instructions, describe its role as an academic assistant for research, writing, and review.
3. Upload the files in [`knowledge/`](knowledge/) following [`UPLOAD_ORDER.txt`](knowledge/UPLOAD_ORDER.txt).
4. Customize `03-domain-profile.md`, `04-personal-style-guide.md`, and `05-journal-profiles.md` for your field, target journals, and personal style.
5. Use the commands or task names in a normal conversation with the GPT.

## Main Commands

| Command | Expected behavior |
|---|---|
| `/new-project [topic]` | Starts a project from an idea. Asks about field, objective, audience, project status, and available data. Produces an initial specification with question, motivation, relevant literature, possible data, tentative strategy, paper structure, and next steps. |
| `/discover interview` | Interviews the user step by step to turn a vague idea into a clear research specification. Asks about phenomenon, question, mechanism, data, method, contribution, and risks. |
| `/discover lit` | Supports literature review. Asks for topic, discipline, paper type, and known references. If the GPT has web access, it should verify the literature; otherwise it should mark references as pending verification. |
| `/discover data` | Explores possible data. Identifies unit of analysis, required variables, population, period, geography, and access restrictions. |
| `/strategize [question]` | Designs the paper strategy. Classifies the paper type and proposes estimand, assumptions, tentative model, threats, robustness checks, and necessary evidence. |
| `/analyze [dataset]` | Plans or interprets empirical analysis. If data are available, describes structure, variables, cleaning, descriptives, models, and robustness. If no data are available, produces an analysis plan. It must not invent results. |
| `/write [section]` | Drafts or revises a section: abstract, introduction, literature, theory, data, methods, results, or conclusion. First identifies the main argument, paragraph functions, and available evidence. |
| `/review [file]` | Acts as a critical reviewer. Separates problems of argument, structure, evidence, method, and style. For a full paper, it may provide priorities or a score. |
| `/revise [report]` | Converts comments, referee reports, or feedback into a revision plan. Classifies comments as critical, important, minor, or taste-based; proposes responses and manuscript changes. |
| `/talk [format]` | Converts the paper into a presentation. Asks for the format if unclear: seminar, conference, job market, or lightning talk. |
| `/submit [journal]` | Runs a pre-submission checklist: journal fit, contribution clarity, methodological strength, tables, figures, bibliography, replicability, and rejection risks. |
| `/tools [task]` | Gives operational checklists and instructions. In ChatGPT, it must not pretend to have run commands, compiled files, or checked git unless it has real access to those tools. |

## Recommended Workflow

1. **Define the project:** use `/new-project` or `/discover interview`.
2. **Map the literature:** use `/discover lit` or `/research-ideation`.
3. **Evaluate data:** use `/discover data` or `/data-analysis`.
4. **Design the strategy:** use `/strategize`.
5. **Draft:** use `/write`, `/paper-draft`, or a direct section request.
6. **Review:** use `/review` for critical diagnosis.
7. **Respond to feedback:** use `/revise`.
8. **Prepare output:** use `/talk` or `/submit`.

## Agent Principles

- **Do not invent evidence.** If data, results, or verified citations are missing, say so clearly.
- **Separate diagnosis from drafting.** Identify problems first, then propose changes.
- **Keep human control.** The user decides the final argument, reported results, and submission choices.
- **Adapt to the field.** The agent should use the disciplinary profile and target journals to calibrate judgment.
- **Prioritize academic clarity.** Every suggestion should improve contribution, identification, evidence, structure, or style.

## Repository Structure

```text
GPT-Author/
|-- README.md
|-- knowledge/
|   |-- UPLOAD_ORDER.txt
|   |-- 01-chatgpt-readme.md
|   |-- 02-workflow-quick-ref.md
|   |-- 03-domain-profile.md
|   |-- ...
|   `-- 20-skill-review.md
```

## Customization

The three most important files for adapting the agent are:

- [`knowledge/03-domain-profile.md`](knowledge/03-domain-profile.md): field, journals, methods, data sources, and standards.
- [`knowledge/04-personal-style-guide.md`](knowledge/04-personal-style-guide.md): voice, tone, paragraph structure, and writing preferences.
- [`knowledge/05-journal-profiles.md`](knowledge/05-journal-profiles.md): target journals, expectations, and review criteria.

## Limitations

- The agent provides academic support; it does not replace human review.
- Simulated review is not equivalent to real referees.
- Quality scores are heuristics, not publication predictions.
- If ChatGPT does not have web access, every new reference must be marked as pending verification.
- If ChatGPT does not have access to external files or local tools, it must not claim that it ran commands or validated outputs.

## License

MIT License. You can adapt this knowledge base to your own research workflow.

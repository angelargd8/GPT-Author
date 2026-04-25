# .codex Project Layer

Esta carpeta adapta la infraestructura original de `.claude/` para uso con ChatGPT/Codex.

## Migrated

- `skills/`: workflows Codex-native con frontmatter valido y metadatos UI en `agents/openai.yaml`.
- `references/`: perfiles de dominio, estilos personales, journals y estandares de codigo.
- `references/agent-profiles/`: roles migrados desde los agentes Claude como perfiles/checklists consultables.
- `rules/`: invariantes, estandares de contenido, calidad, revision y formato de working paper.
- `WORKFLOW_QUICK_REF.md`: referencia rapida del pipeline adaptada a Codex.
- `scripts/lint-scripts.sh`: linter mecanico opcional para scripts R, Python y Julia.
- `state/obsidian-config.md.example`: plantilla opcional para integrar `/checkpoint` con Obsidian.

## Not Migrated Directly

- `.claude/hooks/`: son hooks especificos de Claude Code y shell scripts de automatizacion. Codex debe ejecutar validaciones explicitamente cuando sean necesarias.
- `.claude/settings.json`: configuracion especifica de Claude.
- `.claude/state/obsidian-config.md`: si existe, seria configuracion local privada; no se copia automaticamente. Solo se migra el `.example`.

## Usage

Las instrucciones principales para Codex estan en `AGENTS.md`. Cuando el usuario invoque un comando tipo `/write`, `/review` o `/data-analysis`, leer la skill correspondiente en `.codex/skills/` y, si hace falta, consultar reglas y perfiles en esta carpeta.

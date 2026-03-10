## coding-agents

Repositorio para definir reglas operativas (`rules/`) y habilidades reutilizables (`skills/`) para agentes de desarrollo.

## Estructura

- `rules/`: políticas y convenciones que guían el comportamiento del agente.
- `skills/`: capacidades especializadas con instrucciones ejecutables y referencias.

### Reglas actuales

- `rules/commit-style.md`: formato de mensajes de commit.
- `rules/checkpoint.md`: checkpoints durante cambios lógicos.
- `rules/ephemeral-worktrees.md`: uso de worktrees efímeros para cambios no triviales.

### Skills actuales

- `skills/ephemeral-worktree/SKILL.md`: workflow para implementar cambios en un worktree temporal.
- `skills/ephemeral-worktree/references/worktree-workflow.md`: referencia detallada de pasos, comandos y limpieza.
- `skills/go-mockery/SKILL.md`: generación automática de mocks con mockery.

## Cómo se relacionan `rules` y `skills`

- Las `rules` definen el marco obligatorio (qué se debe cumplir).
- Las `skills` definen el procedimiento concreto (cómo ejecutarlo).
- Ejemplo: la regla `ephemeral-worktrees` exige aislamiento; la skill `ephemeral-worktree` entrega el flujo paso a paso para cumplirlo.

## Uso con `skills.sh`

Este repositorio está preparado para consumir skills vía `skills.sh`.

Flujo recomendado:

1. Cargar la skill requerida (por ejemplo, `ephemeral-worktree`).
2. Seguir las reglas aplicables en `rules/` durante toda la ejecución.
3. Usar el contenido de `references/` como guía operativa detallada.

Notas:

- Mantén cada skill autocontenida en su carpeta bajo `skills/`.
- Define metadatos en `SKILL.md` (`name`, `description`) para facilitar carga y descubrimiento.
- Si agregas nuevas reglas, enlázalas desde la skill correspondiente para mantener trazabilidad entre política y ejecución.

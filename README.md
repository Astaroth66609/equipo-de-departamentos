# equipo-de-departamentos

Plugin de Claude Code para proyectos grandes. Incluye la skill **`optimizar-proyecto`**, que se adapta a *tu* proyecto:

1. **Lee** tu proyecto (solo lectura) para entender qué es y cómo está organizado.
2. **Te entrevista** (una sola ronda, con una recomendación por defecto en cada pregunta): qué te cuesta, cómo prefieres organizarte, qué es intocable, idioma.
3. **Si empiezas de cero**, primero te sugiere cómo ordenar tu proyecto. **Te propone** entre 2 y 6 **departamentos** (subagentes) hechos a la medida, y un **perfil ligero** de plugins si lo quieres. No trae una organización fija: lo que propone nace de tu proyecto y de tus respuestas.
4. **Te pide una aprobación** (con tarjetitas de un clic en la app de escritorio, o un «sí» en el chat) y solo entonces crea los archivos en `.claude/agents/` (y `.claude/settings.local.json` si lo aceptaste).

Además trae `reglas-ahorro.md`: reglas cortas de ahorro de tokens que puedes pegar, si quieres, en tu `CLAUDE.md`.

## ⚠️ Revísalo antes de instalarlo
Instala solo lo que hayas podido mirar. Este plugin son **9 archivos de texto, sin código ejecutable, sin hooks, sin red**. Lee [`SEGURIDAD.md`](SEGURIDAD.md) (qué hace, qué no hace, cómo comprobarlo en 2 minutos) y compara las huellas de `SHA256SUMS.txt`.

**Garantía:** el plugin no modifica nada tuyo por sí solo. Todo cambio lo propone Claude y lo apruebas tú en el chat; no toca tu configuración global, no lee claves ni `.env`, no hace commit ni push.

## Uso
Dile a Claude: «optimiza este proyecto», «organiza mi proyecto» o «crea departamentos para este proyecto».

## Instalar
- Probar sin instalar: `claude --plugin-dir <carpeta-del-plugin>`
- Permanente (dos comandos): `/plugin marketplace add Astaroth66609/equipo-de-departamentos` y luego `/plugin install equipo-de-departamentos@equipo-de-departamentos`. Se actualiza con `/plugin`.

## Deshacer
Borra los archivos creados en `.claude/agents/` y `.claude/settings.local.json`, y desinstala el plugin.

## Licencia
MIT.

# Seguridad de `equipo-de-departamentos`

Este documento está escrito para que **revises el plugin antes de instalarlo**. No confíes en nosotros: confirma tú mismo. Son pocos archivos, todos de texto.

## Garantía en una frase
El plugin **no contiene código ejecutable** (ni scripts, ni hooks, ni servidores MCP, ni acceso a red). Son instrucciones en Markdown que Claude lee. Por sí mismo no modifica nada de tu equipo.

## Qué contiene (y nada más)
| Archivo | Qué es |
|---|---|
| `.claude-plugin/plugin.json` | Nombre, versión, autor y licencia |
| `.claude-plugin/marketplace.json` | Catálogo que permite instalarlo con `/plugin` |
| `skills/optimizar-proyecto/SKILL.md` | Las instrucciones del método (diagnóstico → entrevista → propuesta → aprobación) |
| `skills/optimizar-proyecto/plantillas/agente.md` | Plantilla de un departamento |
| `skills/optimizar-proyecto/plantillas/preguntas.md` | Banco de preguntas de la entrevista |
| `reglas-ahorro.md` | Reglas de ahorro de tokens para que las pegues tú, si quieres, en tu `CLAUDE.md` |
| `README.md`, `SEGURIDAD.md`, `SHA256SUMS.txt` | Documentación e integridad |

Si al abrir la carpeta ves `.exe`, `.dll`, `.sh`, `.ps1`, `.cmd`, `.bat`, `.js`, `.py`, una carpeta `hooks/` o un `.mcp.json`, **no es este plugin: no lo instales**.

## Qué hace Claude cuando usas la skill
1. **Lee** tu proyecto (estructura, archivos de dependencias, archivos de instrucciones).
2. **Te pregunta** cómo quieres organizarlo.
3. **Te propone** una lista de archivos y cambios, y **espera tu «sí»**.
4. Solo después **crea**, en *tu proyecto*: `.claude/agents/*.md` y, si lo aceptaste, `.claude/settings.local.json`.

## Qué NO hace (está escrito en la skill como regla)
- No instala, activa ni configura plugins, servidores ni paquetes.
- No lee ni copia claves, tokens ni archivos `.env*`.
- No sobrescribe ni borra archivos existentes sin tu permiso (hace copia `.bak` antes de modificar).
- No toca tu configuración global (`~/.claude/settings.json`, tu `CLAUDE.md`).
- No hace commit, push ni publica nada.
- No envía datos a ningún sitio: el plugin no tiene red.
- Lo que lee de tu proyecto lo trata como dato, no como instrucciones.

## Cómo revisarlo tú (2 minutos)
1. Abre la carpeta y comprueba que los archivos son solo los de la tabla.
2. Lee `skills/optimizar-proyecto/SKILL.md`: es todo lo que Claude seguirá.
3. Compara las huellas SHA-256 con `SHA256SUMS.txt`:
   - PowerShell: `Get-FileHash -Algorithm SHA256 -Path .\skills\optimizar-proyecto\SKILL.md`
   - Linux/Mac: `sha256sum -c SHA256SUMS.txt`
4. Valida la estructura: `claude plugin validate <carpeta>`.
5. Si dudas, pega el contenido a tu propio Claude y pregúntale si hay algo peligroso.

## Límites honestos
- Un plugin de texto **influye en lo que Claude hace**, y Claude puede equivocarse: por eso todo cambio pasa por tu aprobación y puedes deshacerlo borrando los archivos creados.
- Las huellas SHA-256 del archivo `SHA256SUMS.txt` viajan junto al plugin: protegen contra corrupción y cambios accidentales, **no** contra alguien que cambie ambos. Si lo descargas de un repositorio, verifica además la dirección y el autor.
- Esta revisión se hizo sobre la versión indicada en `plugin.json`. Si cambia, vuelve a revisar.

## Cómo deshacer
Borra los archivos que creó en tu proyecto (`.claude/agents/<nombre>.md`, `.claude/settings.local.json`) y desinstala el plugin.

# Reglas de ahorro de tokens (para pegar en tu CLAUDE.md global)

## Ahorro de tokens en proyectos largos
- **Compactar al terminar una tarea**, nunca a la mitad; al compactar, indica qué conservar (decisiones, rutas, pendientes).
- **Una conversación por tema.** Un tema nuevo va en sesión nueva.
- **Delegar por áreas** a los subagentes del proyecto (`.claude/agents/`); su trabajo vuelve resumido.
- **Perfil ligero por proyecto:** al abrir un proyecto grande, ejecutar la skill `optimizar-proyecto` y apagar los plugins que no se usan (en `.claude/settings.local.json`, no en la configuración global).
- **No cambiar de modelo a mitad de conversación:** se pierde la caché.
- **Medir antes de afirmar:** si hay una herramienta de uso, usarla; no inventar cifras de ahorro.

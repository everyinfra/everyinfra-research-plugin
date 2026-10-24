# EveryInfra Research — Verificación con varias fuentes y lagunas de evidencia a la vista

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/hero-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="assets/hero-light.svg">
    <img alt="La afirmación de que la Torre Eiffel mide 330 metros se contrasta con tres fuentes: dos coinciden y la cifra antigua de 324 metros se explica por la antena añadida en 2022." src="assets/hero-light.svg" width="100%">
  </picture>
</p>

<p align="center">
  <a href="https://cursor.com/en/install-mcp?name=everyinfra&config=eyJ1cmwiOiJodHRwczovL2FwaS5ldmVyeWluZnJhLmNvbS9tY3AiLCJoZWFkZXJzIjp7IkF1dGhvcml6YXRpb24iOiJCZWFyZXIgPEFQSSBLZXk%2BIn19"><img src="https://img.shields.io/badge/Instalar_en_Cursor-2F363D?style=for-the-badge&logo=cursor&logoColor=white" alt="Instalar en Cursor"></a>
  <a href="https://vscode.dev/redirect/mcp/install?name=everyinfra&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.everyinfra.com%2Fmcp%22%2C%22headers%22%3A%7B%22Authorization%22%3A%22Bearer%20%3CAPI%20Key%3E%22%7D%7D"><img src="https://img.shields.io/badge/Instalar_en_VS_Code-0065A9?style=for-the-badge&logo=githubcopilot&logoColor=white" alt="Instalar en VS Code"></a>
  <a href="https://github.com/everyinfra/everyinfra-agent-plugins/blob/main/i18n/README.es.md#claude-code"><img src="https://img.shields.io/badge/Claude_Code-un_comando-B4532A?style=for-the-badge&logo=claude&logoColor=white" alt="Claude Code: un comando"></a>
  <a href="https://github.com/everyinfra/everyinfra-agent-plugins/blob/main/i18n/README.es.md#codex"><img src="https://img.shields.io/badge/Codex-un_comando-2F363D?style=for-the-badge" alt="Codex: un comando"></a>
</p>

<p align="center">
  <a href="https://github.com/everyinfra/everyinfra-agent-plugins/stargazers"><img src="https://img.shields.io/github/stars/everyinfra/everyinfra-agent-plugins?style=social" alt="GitHub stars of everyinfra-agent-plugins"></a>
  &nbsp;<b>Dale una estrella al repo principal y recibe $1 de saldo.</b> <a href="https://everyinfra.com/es/docs?utm_source=github&utm_medium=readme&utm_campaign=everyinfra-research-plugin&utm_content=star_line#quickstart">Cómo reclamarlo →</a>
</p>

<p align="center"><a href="README.md">English</a> · <a href="README.zh-CN.md">简体中文</a> · <b>Español</b></p>

> [!TIP]
> **Este repositorio contiene una sola skill: EveryInfra Research.** El plugin completo de EveryInfra (10 skills, el servidor MCP remoto en `https://api.everyinfra.com/mcp` y la configuración para Claude Code, Codex, Cursor y VS Code) está en **[everyinfra/everyinfra-agent-plugins](https://github.com/everyinfra/everyinfra-agent-plugins)**. Los botones de arriba conectan el servidor MCP; la instalación del plugin en cada entorno está en el repo principal.

[Configuración](docs/setup.md) · [Flujo de trabajo](docs/workflow.md) · [Prompts](examples/prompts.md) · [Referencia de capacidades](docs/reference.md) · [Documentación de la API](https://api.everyinfra.com/docs) <sub>(en inglés)</sub>

EveryInfra Research es una skill independiente para verificar hechos con varias fuentes usando EverySearch MCP. Acota una afirmación actual, compara las fuentes originales y sus fechas, y llega a una conclusión citada en la que las contradicciones y las lagunas quedan explícitas.

EverySearch recupera el material; Research añade la definición de la afirmación, la comparación de fuentes y una conclusión proporcionada a la evidencia. No sustituye el criterio profesional en decisiones de alto riesgo.

## Qué puedes hacer

- Fijar la afirmación concreta con su fecha, jurisdicción, versión y alcance.
- Comparar fuentes originales y separar la fecha de publicación de la fecha del hecho.
- Entregar una conclusión citada con acuerdos, contradicciones y lagunas por separado.

## Instalación

Es un paquete independiente con una sola skill y un flujo de trabajo **MCP**; no es un servicio nuevo. Necesita un entorno de agente compatible y el acceso configurado que describe la [guía de configuración](docs/setup.md). Validar el paquete en local no demuestra que la API esté disponible.

Revisa el contenido del repositorio y luego instálalo en Codex. Estos comandos añaden un catálogo respaldado por GitHub, no un aval de ningún marketplace oficial:

```bash
codex plugin marketplace add everyinfra/everyinfra-research-plugin
codex plugin add everyinfra-research@everyinfra-research-plugin
```

Para una copia local, cambia la fuente del primer comando por `.`. La [guía de configuración](docs/setup.md) también cubre Claude Code y la conexión al servicio, que va aparte.

Con el acceso configurado, prueba:

> Verifica esta afirmación sobre un producto a la fecha que te indico. Da prioridad a la documentación original y separa los hechos confirmados de las lagunas.

Este primer prompt solo inspecciona o prepara. Revisa cualquier operación de pago o efecto externo antes de seguir.

## Cómo funciona

1. Escribe la afirmación o la pregunta de decisión concreta, con su fecha, jurisdicción, versión y alcance.
2. Descubre `everyinfra_search` y el esquema en vivo de `crosscheck`.
3. Mantén separados los mecanismos de búsqueda. Repetir búsquedas por palabra clave no cuenta como corroboración independiente.
4. Revisa las URL originales y la fecha de cada fuente; distingue la fecha de publicación de la del hecho cuando importe.
5. Informa de acuerdos, contradicciones y lagunas y da una conclusión que no vaya más allá de la evidencia.

**Un buen resultado:** una afirmación concisa, una conclusión acotada, los enlaces originales que la respaldan, las fechas relevantes y una sección explícita de incertidumbre, de modo que quien lea pueda ver por qué se sigue la conclusión.

## Límites y seguridad

- Una vía de búsqueda vacía o no disponible es incertidumbre, no prueba de que la afirmación sea falsa.
- Mecanismos independientes no implican automáticamente editores ni evidencias independientes.
- No se garantiza poder resolver cualquier afirmación actual, ni se inventan porcentajes de confianza.

El paquete trae una sola skill: no concede permisos ni registra una segunda conexión MCP. No pongas credenciales en prompts, archivos del repositorio, capturas ni registros compartidos. Descubrir, ejecutar, cobrar y obtener un resultado externo final son estados distintos. Consulta la [política de seguridad](SECURITY.md).

## Preguntas frecuentes y validación

Las preguntas frecuentes, la comprobación sin conexión (`python3 scripts/validate.py`) y la guía para contribuir están en el [README en inglés](README.md#frequently-asked-questions).

Mantenido por [EveryInfra](https://everyinfra.com/es?utm_source=github&utm_medium=readme&utm_campaign=everyinfra-research-plugin&utm_content=footer). Licencia [Apache-2.0](LICENSE).

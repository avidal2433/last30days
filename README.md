# last30days

Proyecto que instala la skill [`last30days`](https://github.com/mvanhorn/last30days-skill)
de Matt Van Horn para investigar cualquier tema con lo que la gente realmente dijo
en los últimos 30 días: Reddit, X, YouTube, TikTok, Hacker News, Polymarket, GitHub
y más, puntuado por engagement real en lugar de por editores.

## Uso

Desde una sesión de Claude Code abierta en este repositorio:

```
/last30days nvidia earnings reaction
/last30days qué está explotando en agentes de IA
/last30days doctor          # diagnóstico de fuentes
```

La skill vive en `.claude/skills/last30days/`, así que se carga automáticamente
en cualquier sesión que trabaje sobre este repositorio (Claude Code local, web o
las sesiones de este proyecto). No hace falta instalar nada más.

## Requisitos

- **Python 3.12+** (obligatorio; la skill se detiene con un mensaje claro en versiones anteriores)
- **Node.js** para el cliente vendorizado de búsqueda en X

Sin ninguna API key funcionan ya: Reddit, Hacker News, Polymarket, GitHub y
búsqueda web. Las claves opcionales (`SCRAPECREATORS_API_KEY`, `X_BEARER_TOKEN`,
`PERPLEXITY_API_KEY`, etc.) amplían la cobertura a TikTok, Instagram, X y otras
fuentes.

Comprueba qué está disponible sin lanzar ninguna investigación:

```bash
python3.12 .claude/skills/last30days/scripts/last30days.py --preflight
```

## Documentación

- [`docs/last30days/README.es.md`](docs/last30days/README.es.md) — guía completa en español
- [`docs/last30days/CONFIGURATION.md`](docs/last30days/CONFIGURATION.md) — todas las variables de entorno y fuentes
- [`docs/last30days/CONCEPTS.md`](docs/last30days/CONCEPTS.md) — cómo funciona el pipeline

## Origen y actualización

| | |
|---|---|
| Upstream | https://github.com/mvanhorn/last30days-skill |
| Versión | 3.25.0 |
| Commit | `349ca444b4fda466e74d471dffa2aff36bb997f1` |
| Licencia | MIT (ver `.claude/skills/last30days/LICENSE`) |

La copia de `.claude/skills/last30days/` es el árbol `skills/last30days/` del
upstream sin la carpeta `assets/` (14 MB de medios de demostración que el runtime
nunca lee). Para actualizar, vuelve a copiar ese árbol desde una versión más
reciente del upstream.

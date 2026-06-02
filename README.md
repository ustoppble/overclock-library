# Overclock Library

Marketplace de **squads multi-agente** prontos para instalar e rodar no Claude Code. Cada squad é um plugin que empacota os agentes, o MCP e as instruções do pipeline — você instala com um comando e executa.

> Catálogo visual e passo a passo: https://overclock.sh/squads

## Adicionar o marketplace

```
/plugin marketplace add ustoppble/overclock-library
```

## Squads disponíveis

| Plugin | O que entrega | Instalar |
|--------|---------------|----------|
| `absurd-landing-squad` | Landing page premium fiel ao DNA visual de uma referência (8 agentes, sem backend) | `/plugin install absurd-landing-squad@overclock` |

## Como funciona

Cada plugin traz:

- `agents/` — os agentes do pipeline (scouts, executors, reviewer)
- `.mcp.json` — os MCP servers usados (ex: `mcp-image`)
- `README.md` — pipeline com gates, skills complementares e missão de exemplo

Skills de terceiros (ex: `higgsfield`, `imagegen`) são referenciadas no README de cada squad e instaladas à parte, respeitando a licença de origem.

## Licença

MIT © Overclock — https://overclock.sh

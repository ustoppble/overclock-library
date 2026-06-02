# Absurd Landing Squad

Squad multi-agente do Overclock que entrega **uma landing page premium** espelhando uma referência visual. Zero backend, zero genérico — fidelidade ao DNA visual da referência é inegociável.

> Resultado real e passo a passo: https://overclock.sh/squads/absurd-landing-squad

## Instalar

```
/plugin marketplace add ustoppble/overclock-library
/plugin install absurd-landing-squad@overclock
```

Isso instala os **8 agentes** e o **MCP `mcp-image`** (config). Exporte sua chave antes de gerar imagem:

```
export OPENAI_API_KEY=...        # ou use GEMINI com IMAGE_PROVIDER=gemini
```

### Skills complementares (terceiros — instale à parte)

```
git clone --depth 1 https://github.com/OSideMedia/higgsfield-ai-prompt-skill ~/.claude/skills/higgsfield
npx claude-code-templates@latest --skill creative-design/imagegen -y -d ~/.claude
```

## O que vem no pacote

| Papel | Agente |
|-------|--------|
| SCOUT | `screenshot-ui-analyzer` |
| SCOUT | `ux-researcher` |
| EXECUTOR | `content-marketer` |
| EXECUTOR | `ui-designer` |
| EXECUTOR | `prompt-engineer` |
| EXECUTOR | `expert-react-frontend-engineer` |
| EXECUTOR | `frontend-developer` |
| REVIEWER | `screenshot-reviewer` |

MCP: `mcp-image` (geração de imagem on-brand via `generate_image`).

## Pipeline (gates fixos)

1. **SCOUT** screenshot-ui-analyzer — extrai o DNA visual da URL (paleta hex, tipografia, spacing). GATE: nada inventado.
2. **SCOUT** ux-researcher — arquitetura de informação da landing. GATE: toda seção mapeada, nenhum slot órfão.
3. **EXECUTOR** content-marketer — copy real por seção. GATE: zero placeholder, zero lorem ipsum. *(paralelo com 4)*
4. **EXECUTOR** ui-designer — design system a partir do DNA. GATE: todos os tokens derivam do DNA. *(paralelo com 3)*
5. **EXECUTOR** prompt-engineer — prompts + render via `mcp-image`. GATE: nenhum slot de imagem vazio.
6. **EXECUTOR** expert-react-frontend-engineer — estrutura React responsiva. GATE: componentes sem conteúdo (estrutura pura).
7. **EXECUTOR** frontend-developer — monta a landing final. GATE: compila + responsivo + fiel ao DNA.
8. **REVIEWER** screenshot-reviewer — QA por camada. GATE: PASS em todas. 1 redo por camada.

## Missão de exemplo

```
aqui ta o site do concorrente: https://vitality.gg/ e eu quero fazer um site pro meu time de CS chamado Overclock. decida sozinho
```

## Licença

MIT © Overclock

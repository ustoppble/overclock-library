# Absurd Landing Squad

Squad multi-agente do **Overclock** que entrega **uma landing page premium** espelhando uma referência visual. Zero backend, zero genérico — fidelidade ao DNA visual da referência é inegociável.

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

| Papel | Agente | Função |
|-------|--------|--------|
| SCOUT | `oc-dna-scout` | extrai o DNA visual da referência (paleta hex, tipografia, spacing) |
| SCOUT | `oc-blueprint-scout` | monta a arquitetura de informação da landing |
| EXECUTOR | `oc-copysmith` | escreve a copy real de cada seção |
| EXECUTOR | `oc-tokensmith` | constrói o design system a partir do DNA |
| EXECUTOR | `oc-image-director` | gera os prompts e renderiza as imagens (mcp-image) |
| EXECUTOR | `oc-structure-engineer` | estrutura React responsiva (sem conteúdo) |
| EXECUTOR | `oc-assembler` | monta a landing final |
| REVIEWER | `oc-qa-sentinel` | QA por camada, gate final |

MCP: `mcp-image` (geração de imagem on-brand via `generate_image`).

## Pipeline (gates fixos)

1. **SCOUT** `oc-dna-scout` — DNA visual da URL (paleta hex, tipografia, spacing). GATE: nada inventado.
2. **SCOUT** `oc-blueprint-scout` — arquitetura de informação. GATE: toda seção mapeada, nenhum slot órfão.
3. **EXECUTOR** `oc-copysmith` — copy real por seção. GATE: zero placeholder, zero lorem ipsum. *(paralelo com 4)*
4. **EXECUTOR** `oc-tokensmith` — design system do DNA. GATE: todos os tokens derivam do DNA. *(paralelo com 3)*
5. **EXECUTOR** `oc-image-director` — prompts + render via `mcp-image`. GATE: nenhum slot de imagem vazio.
6. **EXECUTOR** `oc-structure-engineer` — estrutura React responsiva. GATE: componentes sem conteúdo (estrutura pura).
7. **EXECUTOR** `oc-assembler` — monta a landing final. GATE: compila + responsivo + fiel ao DNA.
8. **REVIEWER** `oc-qa-sentinel` — QA por camada. GATE: PASS em todas. 1 redo por camada.

## Missão de exemplo

```
aqui ta o site do concorrente: https://vitality.gg/ e eu quero fazer um site pro meu time de CS chamado Overclock. decida sozinho
```

## Licença

MIT © Overclock — https://overclock.sh

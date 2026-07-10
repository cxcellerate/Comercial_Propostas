# Comercial — Propostas CXcellerate

Repositório central das propostas comerciais da CXcellerate, mantido por toda a equipe.

## Estrutura
- `Clientes/<Empresa> - <AAAA-MM-DD>/` — uma pasta por cliente/atendimento:
  - `dossie-<empresa>.md` — pesquisa do cliente (Fase 1)
  - `proposta-<cliente>.html` — proposta base (copy neutra)
  - `proposta-<cliente>-v2.html` — proposta com copy persuasiva
  - `_index.md` — índice do atendimento
- `Logo CXcellerate/` — assets de marca
- `.claude/skills/` — skills do Claude Code compartilhadas pela equipe
- `*.png`, `apresentacao-cxcellerate.html` — assets e deck institucional compartilhados

## Skill `pesquisar-cliente-proposta`

As propostas deste repositório são geradas com a skill **`pesquisar-cliente-proposta`**, que está versionada aqui em [`.claude/skills/pesquisar-cliente-proposta/`](.claude/skills/pesquisar-cliente-proposta/) (instruções em `SKILL.md` + template `proposta-template.html`).

**Como usar (Fabiana e equipe):**
1. Clone este repositório e abra a pasta no Claude Code — a skill é carregada automaticamente como skill do projeto, sem instalação.
2. Ao receber um pedido de orçamento/briefing de um cliente, peça algo como *"montar proposta para o cliente X"* ou *"pesquisar o cliente Y"* — a skill dispara sozinha nesses casos.
3. Ela pesquisa a empresa, gera o dossiê (Fase 1) e a proposta em HTML na pasta `Clientes/<Empresa> - <data>/`.

Para usar a skill fora deste repositório, copie a pasta `pesquisar-cliente-proposta` para `~/.claude/skills/` (ela fica disponível em qualquer projeto).

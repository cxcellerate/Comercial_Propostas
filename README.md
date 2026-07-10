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

## Skill `criar-contrato-prestacao-servicos`

Gera a **minuta de contrato de prestação de serviços** (HTML em papel timbrado CXcellerate, direito brasileiro) a partir de uma proposta aprovada. Versionada em [`.claude/skills/criar-contrato-prestacao-servicos/`](.claude/skills/criar-contrato-prestacao-servicos/) (instruções em `SKILL.md` + `contrato-template.html`).

**Como usar:** com o repositório aberto no Claude Code, peça *"gerar o contrato do cliente X"* após a proposta fechar — a skill lê a proposta, o dossiê e o `_index.md` da pasta do cliente e gera `contrato-<cliente>-prestacao-servicos.html` com os padrões da casa (garantia 90 dias, foro Santo André/SP, PIX à vista com 10% de desconto). Campos desconhecidos ficam destacados em magenta para preencher antes da assinatura. **Toda minuta deve ser revisada por advogado antes de assinar.**

## Skill `legal-assistant`

Skill de **análise e revisão de contratos** (em [`.claude/skills/legal-assistant/`](.claude/skills/legal-assistant/)): identifica cláusulas de risco, traduz juridiquês, destaca obrigações e sugere pontos de negociação. Usar para auditar contratos recebidos de terceiros ou revisar as próprias minutas (ex.: *"analise este contrato"*). Fornece orientação informativa — **não substitui advogado**.

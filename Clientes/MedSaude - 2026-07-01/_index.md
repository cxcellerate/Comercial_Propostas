# MedSaude — 01/07/2026

## Contexto
- **Contatos:** Leandro e Tânia
- **Projeto:** E-commerce para público diabético (**50 produtos iniciais**, com novas adições ao longo dos meses) com **foco em assinatura** (fidelização) + **App iOS/Android** (usuário, histórico, fidelidade/cashback, conteúdos informativos com indicação de equipamentos, push de promoções).
- ⚠️ **O APP NÃO VENDE** — toda compra acontece no site; o app é relacionamento/fidelização e leva o cliente de volta ao site.
- **Cliente não tem nenhum canal digital hoje.** Venda 100% no canal próprio (**site** — SEM marketplaces); o site converte tráfego de influenciadores/anúncios em **assinantes**.
- Site clean e educativo — blog para SEO/AEO (ser achado no Google e nas IAs).
- Referência negativa: supersaudavelshopping.com.br · Referência positiva: sibionics.com.br

## Comercial
- **Valor:** R$ 37.900,00 total, discriminado em **Web R$ 26.000** (e-commerce com assinaturas) + **Apps iOS/Android R$ 11.900** (adaptação da base proprietária CXcellerate)
- **Cadastro dos até 50 produtos do lançamento incluído no valor** (a partir do material — fotos/descrições/preços — fornecido pela MedSaude, que é premissa); produtos além disso = pacote de R$ 1.500 (slide 12)
- **Argumento do preço dos apps:** base proprietária pronta + desenvolvimento acelerado (low code interno via Claude Code — na frente do cliente falar "base proprietária, multiplataforma com performance nativa"; evitar as palavras "low code" e "nativo puro")
- Pix à vista −10% = R$ 34.110,00 (economia R$ 3.790) · 50/50 = 2× R$ 18.950,00 · Cartão à vista +3,15% = R$ 39.093,85 · Cartão 12× +12,50% = R$ 42.637,44 (12× R$ 3.553,12) · Âncora diária: R$ 103,84/dia (R$ 93,45 no Pix)
- Pós-lançamento (slide único "11 — Pós-lançamento", 6 cards): **Garantia 90 dias incondicional** (defeitos sem custo, sem consumir horas do suporte) · Suporte CX R$ 770 (R$ 9.240/ano, **12h/mês + garantia técnica de atualização** de sistema e integrações) · **Evolução orçada à parte com aprovação prévia** · Atendimento loja WhatsApp R$ 390 (R$ 4.680/ano, **número novo exclusivo + IA com transbordo humano da MedSaude**) · Fornecedores externos ±R$ 300–350 (~R$ 4.200/ano) · Google Workspace direto ao Google · régua de defeito = **PRD aprovado na semana 2**
- **Gatilho do prazo (slide 06):** as 14 semanas contam **a partir do kickoff com os materiais das Premissas entregues** — no deck está embalado como promessa ("o prazo é compromisso da CXcellerate"), mas a trava jurídica é essa: sem material, sem relógio.
- **Cronograma:** PRD+Design 2 sem (**rodadas de ajuste de design limitadas à janela de 2 semanas** — layout aprovado segue para dev) · Dev 5 sem · Publicação 5 sem (**justificada no slide: revisão App Store/Google Play com fila que reinicia a cada reenvio, homologação de pagamento/frete em produção, pedidos reais**) · Margem 2 sem = **14 semanas (~3,5 meses)**
- Validade: 30 dias

## Arquivos
- `nuvemshop-asaas-ecommerce-research.md` — pesquisa técnica Nuvemshop + Asaas
- `proposta-medsaude.html` — proposta base (copy neutra)
- `proposta-medsaude-v2.html` — proposta com copy persuasiva (hard-copy)
- `contrato-medsaude-prestacao-servicos.html` — minuta de contrato (gerada 10/07/2026, base proposta v2 de 01/07/2026)

## Contrato — minuta gerada em 10/07/2026
- **Valor:** R$ 37.900,00 (Web R$ 26.000 + Apps R$ 11.900) · **Forma no contrato:** PIX à vista com 10% desc = R$ 34.110,00 (padrão da casa — forma fechada NÃO estava registrada aqui)
- Mensalidades (Suporte CX R$ 770, WhatsApp IA R$ 390, pacote catálogo R$ 1.500, tráfego pago) ficaram FORA do valor, listadas na exclusão 1.2 (contratáveis por instrumento próprio/aditivo); fornecedores externos (Nuvemshop, Asaas, logística, servidor/régua, Workspace) na cláusula 6
- Apps: publicação nas contas Apple/Google Developer da CXcellerate sem anuidade para o cliente (item 1.3); código-base licenciado (cláusula 9.2 padrão, sem alteração)
- ⚠️ Minuta gerada por IA — **revisar com advogado antes de assinar**

### Pendências do contrato (campos `<mark>` a preencher)
- [ ] **Confirmar forma de pagamento fechada com o cliente** (contrato saiu com o padrão PIX à vista −10%)
- [ ] Razão social da MedSaude (aparece 2×: qualificação e assinatura)
- [ ] CNPJ da MedSaude
- [ ] Endereço completo da MedSaude, com CEP
- [ ] Representante legal (Leandro ou Tânia?) + CPF (aparece 2×)
- [ ] E-mail oficial da MedSaude para notificações (cláusula 12.3)
- [ ] Local e data de assinatura
- [ ] Nome e CPF das 2 testemunhas
- [ ] Cláusula de continuidade (código liberado se a CX encerrar atividades): decisão em aberto — definir antes de assinar (nota já existente nas respostas engatilhadas)

## Slides-chave (blindagem das perguntas difíceis)
- Slide "05 — Tecnologia": Web = base Nuvemshop + camada CXcellerate · Apps = base proprietária, multiplataforma com performance nativa (responde "como R$ 26k cobre tudo?")
- Slide "08 — Emissão fiscal": **Asaas emite a nota junto com o pagamento** (custo = taxas de transação + valor por nota, sem mensalidade de emissor) · se cliente já tem ERP/contador: mapeamento no PRD, integração com ERP existente (Bling/Tiny) ou emissão pelo Asaas · enquadramento fiscal validado com o contador no PRD (responde "já tenho ERP/contador")
- Slide "11 — Pós-lançamento": ver linha em Comercial (responde "bug na semana 15?"). Workspace saiu deste slide (ficou só em Serviços recomendados).
- Slide "12 — Evolução": processo (pede → orçamento fechado → só executa com aprovação) + pacote destacado **"Crescimento de catálogo & conteúdo — R$ 1.500"**: adição automatizada de **até 50 produtos** (texto + imagens, loja e apps) + 1 reunião de estratégia com marketing (**conteúdo para SEO + fidelização** — é o valor central do pacote) + calendário de publicações mensal. Contexto: catálogo não deve passar de ~50 produtos nem nos próximos meses.
- Slide "13 — Serviços recomendados": Tráfego pago (opcional, à parte) + Workspace com cortesia: **"fechando o projeto, a configuração do e-mail é cortesia da CXcellerate"**
- Slide "14 — Regulatório": ANVISA (AFE/RT = obrigação da MedSaude; CXcellerate entrega em conformidade com o jurídico/RT deles)
- Slide "15 — LGPD": privacy by design sobre a Lei 13.709/2018 · CX entrega: consentimento destacado (Art. 11), direitos do titular (Art. 18), **modelos de documentos LGPD** e documentação legal do que foi construído · MedSaude (controladora): **designa DPO + e-mails de contato** e adequa os modelos com o jurídico dela (também virou premissa no slide 17)
- Slide "16 — Propriedade & contas": tabela 7 linhas — MedSaude: loja Nuvemshop, domínio/marca/conteúdo, dados (LGPD), contas de operação (Asaas, hospedagem, servidor, régua — pagas direto aos fornecedores) e apps publicados com **direito de uso permanente + transferência entre contas de desenvolvedor disponível** · CXcellerate: **contas Apple/Google Developer** (app não vende; anuidades já pagas pela CX) e **código-fonte da base** (licenciado) · rodapé: "se os caminhos se separarem, loja continua vendendo, dados vão com a MedSaude, app segue no ar; encerra-se manutenção/evolução"
- Slide "05 — Tecnologia" também carrega o papel dos canais: **site = canal de aquisição · app = canal de fidelização** (frase na intro + tags nos cards)

## Argumentos das perguntas prováveis (já no deck)
- **Assinatura na prática** → Escopo card 02: assinante troca cartão/endereço pelo app e **cancela quando quiser** (pausar = cancelar; não existe "pular entrega")
- **Rastreio de influenciador** → Escopo card 04: **GA4 + links e cupons por parceiro**
- **Regras de cashback** → Premissas: regras de negócio da MedSaude, rodada de definição na fase de PRD (sistema já cobre as dinâmicas)
- **Régua de comunicação** → Pós-lançamento/Fornecedores externos: operada pela **CXcellerate ou pelo Asaas**, definida no PRD
- **Tráfego pago** → Serviços recomendados: **opcional, conversado à parte** (influenciador = curto prazo, SEO/AEO = médio, tráfego = acelerador)

## Passada Hard Copy nos títulos (02/07/2026)
- 01: "Quem procura hoje, encontra o concorrente." · 04: "Tudo conversa com tudo." · 05: "Por que custa isso — e não o triplo." · 06: "No ar em 3,5 meses." · 10: "Investimento único. Retorno recorrente." · 13: "Para acelerar, quando fizer sentido." · 18: provérbio cortado, fecho na dor concreta ("cada semana de espera é semana que o concorrente atende quem procurou por vocês")

## Definições fechadas (02/07/2026)
- **Blog no lançamento:** 6 artigos iniciais no ar, aprovados pela MedSaude antes da publicação (está no Escopo/Performance)
- **Suporte R$ 770:** mensalidade começa **1 mês após a entrega final** (está no card do slide 11)
- **Cartão 12×:** parcela R$ 3.553,12 · total R$ 42.637,44 (números fecham exatos)
- **Sigla padronizada:** SEO/GEO/AEO em todo o deck · **LGPD em português:** "Privacidade desde o projeto"
- **Capa:** data 01/07/2026 mantida · "Fabiana/Fabi" mantido como está

## Respostas verbais engatilhadas (NÃO estão no deck)
- **"Frete da assinatura embutido ou por envio?"** → depende do fornecedor de logística escolhido no comparativo; preço/embute é definido no PRD junto com a escolha
- **Impressora de cortesia:** se fecharem a proposta completa, CXcellerate envia uma impressora + constrói a padronização de impressão de pedidos (formato depende da logística fechada) — trunfo de fechamento, usar na mesa se precisar
- **"Vendem pro concorrente?"** → "Não costumamos pegar projetos do mesmo segmento, mas não oferecemos exclusividade formal de desenvolvimento — a empresa vive de desenvolvimento."
- **"Me vende o código, quanto custa?"** → buyout da instância: **R$ 120.000** (só verbal, previsto em contrato se pedirem)
- **Cláusula de continuidade** (código liberado se a CX encerrar atividades): decisão ainda em aberto — definir antes de assinar contrato

- **Nuvemshop:** plano recomendado = **Impulso**; valor final das mensalidades externas depende de faturamento mensal + quantidade de produtos (fechado no PRD). Slide 08 cobre gateway alternativo: emissão via ERP integrado (Bling/Tiny).
- ⚠️ **Checar antes da reunião:** a pesquisa técnica indica que a emissão nativa do Asaas é **NFS-e (nota de serviço, só PJ)** — venda de PRODUTO físico normalmente exige NF-e de produto (modelo 55), que costuma sair via ERP (Bling/Tiny). Confirmar com Asaas/contador qual nota a operação MedSaude emitirá; o slide 08 foi escrito para acomodar os dois cenários.

## Notas internas
- ⚠️ NUNCA mencionar outros sites embutidos no valor.
- Slide dos Correios está **oculto** no HTML (class="slide-off" + display:none, eyebrow "XX"); para reexibir, trocar por class="slide" e renumerar. O comparativo de transporte ganhou a nota: "Abriremos um canal com esses fornecedores para a melhor negociação de frete".
- Proposta inclui slides comparativos de gateways de pagamento (10 opções) e logística (6 opções) para o cliente decidir.

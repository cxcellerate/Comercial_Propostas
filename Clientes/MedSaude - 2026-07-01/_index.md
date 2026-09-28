# MedSaude — 01/07/2026

## Contexto
- **Contatos:** Leandro e Tânia
- **Projeto:** E-commerce para público diabético (**50 produtos iniciais**, com novas adições ao longo dos meses) com **foco em assinatura** (fidelização) + **App iOS/Android** (usuário, histórico, fidelidade/cashback, conteúdos informativos com indicação de equipamentos, push de promoções).
- ⚠️ **O APP NÃO VENDE** — toda compra acontece no site; o app é relacionamento/fidelização e leva o cliente de volta ao site.
- **Cliente não tem nenhum canal digital hoje.** Venda 100% no canal próprio (**site** — SEM marketplaces); o site converte tráfego de influenciadores/anúncios em **assinantes**.
- Site clean e educativo — blog para SEO/AEO (ser achado no Google e nas IAs).
- Referência negativa: supersaudavelshopping.com.br · Referência positiva: sibionics.com.br

## Comercial
- **Valor (revisão 28/09/2026 — proposta-medsaude-v2.html):** R$ 29.890,00 total, discriminado em **Web R$ 17.990** (e-commerce com assinaturas) + **Apps iOS/Android R$ 11.900** (adaptação da base proprietária CXcellerate). Valor anterior: R$ 37.900 (Web R$ 26.000).
- **Formas de pagamento (revisão 28/09/2026):** Pix à vista com 3% desc = R$ 28.993,30 · Entrada R$ 15.000 + 6x boleto R$ 2.481,67 · Cartão à vista R$ 30.831,54 (+3,15%) · Cartão 12x R$ 2.802,19 = R$ 33.626,25 (+12,50%)
- **Posicionamento tecnológico (revisão 28/09/2026):** e-commerce e app apresentados como **sistema CXcellerate similar à estrutura da Nuvemshop** (substituiu "Base Nuvemshop + camada CXcellerate" em todos os slides da v2)
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
- `proposta-medsaude-v3.html` — **proposta VIGENTE (28/09/2026, sem app)**: cliente não quis o aplicativo. Removido tudo sobre app iOS/Android do 1º ao último slide (capa, diagnóstico, objetivo, escopo, tecnologia, cronograma, investimento, pós-lançamento, evolução, regulatório, LGPD, propriedade & contas, premissas) e a imagem do ecossistema (slide 04) editada — célula "App" virou "Blog & SEO" e "App de gestão" saiu (`ecossistema-integrado-sem-app.png`). Card "Atendimento da loja por WhatsApp" (R$ 390/mês) retirado do slide 11. Card "Fornecedores externos" sem faixa de R$ 300–350/mês: início com planos gratuitos e upgrade conforme o uso, pago direto aos fornecedores só no upgrade. **Valor: R$ 9.790,00** (só plataforma web; R$ 17.990 − R$ 8.200 por decisão comercial em 28/09/2026) · Pix 3% desc R$ 9.496,30 · Entrada R$ 4.990 + 6x R$ 800 · Cartão à vista R$ 10.098,39 · Cartão 12x R$ 917,81 = R$ 11.013,75
- `proposta-medsaude-v2.html` — proposta com copy persuasiva (hard-copy), revisada em 28/09/2026 com app (superada pela v3, histórico)
- `onboarding-medsaude.html` — formulário de onboarding (28/09/2026, alinhado à proposta v3 sem app e R$ 9.790): 15 seções cobrindo dados para contrato e NF, representante/testemunha, forma de pagamento e opcionais, marca, domínio/acessos, produtos (técnico/ANVISA + lista dos até 50), assinatura, gateway e fiscal, logística, fidelidade, LGPD/DPO, blog/influenciadores, kickoff; seção 14 (WhatsApp com IA) só abre se o cliente marcar "Sim". Salva no navegador (localStorage), exporta/importa JSON e imprime em PDF
- `CXcellerate — Proposta MedSaude 28-09-26.pdf` — export da **v3 (sem app, R$ 9.790)**; A4 paisagem, 19 páginas. A versão com app (R$ 29.890) fica no histórico do git
- `contrato-medsaude-prestacao-servicos-v5.html` — **minuta VIGENTE** (28/09/2026, sem app): v4 alinhada à proposta v3 — objeto só e-commerce com assinaturas (item f de apps removido, 1.3 de contas de desenvolvedor removido, 1.4→1.3), 3.1 = R$ 9.790,00, 3.2 com as 4 formas (PIX 3% desc R$ 9.496,30 · entrada R$ 4.990 + 6x R$ 800 · cartão à vista R$ 10.098,39 · cartão 12x R$ 917,81 = R$ 11.013,75), cronograma sem lojas de apps (14 semanas mantidas), cláusula 6ª com "início com planos gratuitos, upgrade conforme o uso", 9.4 e 12.4 sem apps. WhatsApp IA mantido em 1.2.b como opcional fora do preço
- `contrato-medsaude-prestacao-servicos-v4.html` — minuta v4 (superada em 28/09/2026 pela v5, histórico; com app): v3 alinhada à proposta revisada — objeto sobre o sistema de e-commerce CXcellerate (similar à Nuvemshop), 3.1 = R$ 29.890 (Web R$ 17.990 + Apps R$ 11.900), 3.2 com as 4 formas da proposta (PIX 3% desc R$ 28.993,30 · entrada R$ 15.000 + 6x R$ 2.481,67 · cartão à vista R$ 30.831,54 · cartão 12x R$ 2.802,19), 3.3 reescrita, cláusula 6ª sem linha Nuvemshop (infra da plataforma web entra no conjunto ± R$ 300–350/mês), 9.4 inclui o sistema de e-commerce na base proprietária com a loja licenciada e conta/domínio/dados da MedSaude, referências à proposta de 28/09/2026
- `contrato-medsaude-prestacao-servicos-v3.html` — minuta v3 (superada em 28/09/2026, histórico; 10/07/2026, pós-memorando): v2 + blindagem da base proprietária dos apps (9.4 — resolvia o 🔴 de PI do memorando, Lei 9.609/98), subcontratação (5.2), garantia sem "incondicional" (8.1), LGPD defensiva + incidentes 48h + dados agregados (10.4–10.6 — reforço para dado de saúde), piso de 20% na rescisão (11.2), fallback de pagamento 50/50 (3.3), confidencialidade 5 anos (13.1), não aliciamento (14.6) e sobrevivência (14.7).
- `contrato-medsaude-prestacao-servicos-v2.html` — minuta v2 (superada, histórico; pós-parecer): + cláusula 12ª (obrigação de meio, responsabilidade limitada ao valor pago, força maior), 13ª (confidencialidade recíproca), 7.3 (aprovação tácita do PRD), 3.3 harmonizado (fallback por aditivo); Disposições Gerais → 14ª, Foro → 15ª (e-mail de notificações agora na cláusula 14.3)
- `contrato-medsaude-prestacao-servicos.html` — minuta v1 (superada, histórico)

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

## Referências fora da proposta
- **Planos e taxas do Asaas** (para responder sobre upgrade de plano dos fornecedores externos — não vai no texto da proposta): https://www.asaas.com/precos-e-taxas

## Slides-chave (blindagem das perguntas difíceis)
- Slide "05 — Tecnologia": Web = sistema CXcellerate similar à estrutura da Nuvemshop · Apps = base proprietária, multiplataforma com performance nativa (responde "como R$ 18k cobre tudo?")
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

- **Plataforma web:** na revisão de 28/09/2026 a proposta passou a citar "sistema CXcellerate similar à estrutura da Nuvemshop" (sem citar plano Impulso); valor final das mensalidades externas depende de faturamento mensal + quantidade de produtos (fechado no PRD). Slide 08 cobre gateway alternativo: emissão via ERP integrado (Bling/Tiny).
- ⚠️ **Checar antes da reunião:** a pesquisa técnica indica que a emissão nativa do Asaas é **NFS-e (nota de serviço, só PJ)** — venda de PRODUTO físico normalmente exige NF-e de produto (modelo 55), que costuma sair via ERP (Bling/Tiny). Confirmar com Asaas/contador qual nota a operação MedSaude emitirá; o slide 08 foi escrito para acomodar os dois cenários.

## Notas internas
- ⚠️ NUNCA mencionar outros sites embutidos no valor.
- Slide dos Correios está **oculto** no HTML (class="slide-off" + display:none, eyebrow "XX"); para reexibir, trocar por class="slide" e renumerar. O comparativo de transporte ganhou a nota: "Abriremos um canal com esses fornecedores para a melhor negociação de frete".
- Proposta inclui slides comparativos de gateways de pagamento (10 opções) e logística (6 opções) para o cliente decidir.

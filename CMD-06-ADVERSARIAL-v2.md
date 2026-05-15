# CMD-06-ADVERSARIAL · v2.0
## Adversarial Filter + Cynefin Router · Portfolio Decision System

```
name: CMD-06-ADVERSARIAL
version: 2.0
default-state: TRASH
burden-of-proof: ON-THE-IDEA-TO-SURVIVE
routing: CYNEFIN (Obvious / Complicated / Complex / Pioneer)
philosophy: kill-first / data-reverses / energy-proportional-to-risk
```

---

## 1. CORE PRINCIPLE — Two Layers of Discipline

**Layer 1 — Adversarial Filter (Survival)**  
Default = TRASH. Every idea must pass 4 hard gates + score ≥8/14 on soft gates to survive.

**Layer 2 — Cynefin Router (Energy Allocation)**  
Surviving ideas are NOT treated equally. Each surviving idea gets a domain score 1–15. The action is proportional to the score. Energy invested = proportional to risk of losing the window × value of being recognized as author.

The combined system filters AND prioritizes. You don't waste energy on commodity ideas. You don't lose pioneer ideas to procrastination.

---

## 2. THE FILTER LAYER — 4 Hard Gates + 7 Soft Gates

### HARD GATES — All must pass. One fail = KILL.

| ID | Gate | Pass requires |
|----|------|---------------|
| **HK1** | Anthropic-aligned | Citation + reasoning, not vague claim |
| **HK2** | Original (90-day check) | Date-stamped search + result links |
| **HK3** | Personally used 7+ days | Drive timestamps, chat history, BACKLOG |
| **HK4** | Solo-buildable before Sep 2026 | Concrete scope + time estimate |

### SOFT GATES — Scored 0/1/2. Need ≥8/14 to KEEP.

| ID | Gate | 0 | 1 | 2 |
|----|------|---|---|---|
| **SK1** | Customer evidence | Hypothetical | 1-2 named real | 3+ real with friction |
| **SK2** | Outcome evidence | None | Anecdotal | Numbers |
| **SK3** | Defensibility | Anthropic kills it | Partially survives | Uniquely valuable |
| **SK4** | Composability | Orphan | Partial fit | Fits CMD taxonomy |
| **SK5** | Adversarial survival | Not tested | Light pushback | Hostile critique survived |
| **SK6** | Concept clarity | Unclear | 1 paragraph | 1 sentence to anyone |
| **SK7** | Naming asset | No name | Working name | Sharp/memorable |

### Survival Verdict

```
All HK + SK ≥ 12  →  KEEP-PUBLISH (pode mostrar à Anthropic)
All HK + SK 8-11  →  KEEP-BUILD (constrói, depois publica)
All HK + SK 4-7   →  INCUBATE (notas privadas, não reivindica)
All HK + SK ≤ 3   →  KILL
Qualquer HK fail  →  KILL
```

---

## 3. THE ROUTER LAYER — Cynefin Domain Scoring

After uma ideia sobrevive ao Filtro, ela entra no Roteador. Cynefin classifica em 4 domínios. Cada domínio exige ação diferente.

### Three Multiplied Questions

Para cada ideia que sobreviveu (KEEP-PUBLISH ou KEEP-BUILD), responda:

**Q1: Quão original é a ideia?**  
1 = existe documentada publicamente  
2 = elementos existem, combinação parcial existe  
3 = elementos existem, combinação inédita  
4 = poucos elementos existem  
5 = ninguém viu

**Q2: Quão estreita é a janela antes de outro chegar?**  
1 = anos (commodity)  
2 = 12+ meses  
3 = 6-12 meses  
4 = 3-6 meses  
5 = semanas (AI converge fast)

**Q3: Qual o valor se VOCÊ for reconhecido como autor?**  
1 = irrelevante para tua carreira  
2 = ajuda em currículo  
3 = abre portas específicas  
4 = define posicionamento  
5 = transformador (ex: ser referência num primitivo)

### Score = Q1 × Q2 × Q3 (range 1–125, mas na prática raramente passa de 60)

### Domínio Cynefin → Ação

| Score | Domínio | Ação | Janela | Energia | Investimento |
|-------|---------|------|--------|---------|--------------|
| **1–8** | **Óbvio** | Não publica como descoberta | Anos | Zero | 0h |
| **9–24** | **Complicado** | Publica como tutorial educacional | 6-12 meses | Baixa | 1-3h |
| **25–60** | **Complexo** | Concept paper + repo + nomeia | 60-90 dias | Média | 1-2 semanas |
| **61+** | **Pioneiro** | Sprint imediato de publicação | <30 dias | Alta | 3-7 dias intensivos |

**Regra de proteção proporcional:** A energia gasta é proporcional ao risco de perder × valor de ser reconhecido. Não trata todas as ideias igual. Não desperdiça em commodity, não negligencia pioneer.

---

## 4. XLS SCHEMA — v2 com Cynefin

### Sheet 1: PORTFOLIO

Adições à v1:

| Column | Type | Descrição |
|--------|------|-----------|
| `Q1_originality` | 1-5 | Cynefin Q1 |
| `Q2_window` | 1-5 | Cynefin Q2 |
| `Q3_value_to_you` | 1-5 | Cynefin Q3 |
| `cynefin_score` | formula | =Q1*Q2*Q3 |
| `domain` | formula | Auto-derived: Obvious/Complicated/Complex/Pioneer |
| `action_protocol` | formula | Auto-derived from domain |
| `energy_budget_hours` | formula | Auto-derived: 0 / 1-3 / 40-80 / 25-60 |
| `deadline` | formula | =TODAY() + window_days |

### Lógica de decisão final

```
SE survival = KEEP-PUBLISH AND cynefin = Pioneer:
   → SPRINT (sair em 7 dias, custe o que custar)

SE survival = KEEP-PUBLISH AND cynefin = Complex:
   → CONCEPT FIRST (publicar nome em 30 dias, build em 90)

SE survival = KEEP-BUILD AND cynefin = Complex:
   → BUILD QUIET (60 dias build, depois publica)

SE survival = KEEP AND cynefin = Complicated:
   → TUTORIAL (publica como conteúdo educacional, baixo investimento)

SE survival = INCUBATE OR cynefin = Obvious:
   → ARQUIVA (sem publicação, sem reivindicação)

SE survival = KILL:
   → MORRE (vai para KILL_LOG, nunca re-introduz)
```

---

## 5. RULES UNDER UNCERTAINTY — Como pontuar honestamente

**Regra 1 — Em dúvida, pontue para baixo.** Hipotético não vale.

**Regra 2 — Citação ou nada.** Toda célula com 1+ deve ter comentário com data/link/nome/número. Sem comentário = score 0.

**Regra 3 — kill_argument antes de keep_evidence.** Sempre. Se não articula o argumento contra, não entende a ideia.

**Regra 4 — Adversarial é binário.** Ou alguém crítico tentou matar e falhou, ou não. "Eu pensei sozinho" = 0.

**Regra 5 — Originalidade tem data.** HK2 expira em 90 dias. Re-checa.

**Regra 6 — Re-pontua trimestralmente.** KEEP pode virar KILL quando Anthropic ship native equivalent.

**Regra 7 — Cynefin não é estável.** Window encolhe. Pioneer hoje pode virar Complex em 60 dias. Recheck mensal.

---

## 6. WORKING BACKWARDS — Da meta de 12 meses para hoje

### Meta 12 meses (cenário ideal)
- Renda recorrente $3-8k/mês (consultoria + curso ou cargo Anthropic-adjacent)
- Reputação em 1-2 áreas específicas (não 10 vagas)
- 2-3 ativos públicos gerando inbound (artigo, repo, certificação)
- Network internacional pré-mudança Holanda

### Meta 6 meses
- 1 publicação âncora com >1000 leituras qualificadas
- Ambassador Brasil aprovado OU vaga remota AI-adjacent assinada
- 1 cliente pagante (consultoria/workshop)
- GitHub público com tração mensurável (50+ stars em algum repo)

### Meta 3 meses
- 1 ideia Pioneer publicada e nomeada (claim de prioridade fixado)
- Ambassador candidatura enviada
- 1 prova de conceito real funcionando (você como usuário 30+ dias)
- Primeiros $500-2000 via consultoria 1-on-1

### Meta 30 dias
- Portfolio classificado: Filtro + Cynefin rodados em tudo
- Pioneer ideas (score 61+) publicadas
- Complex ideas (25-60) com concept paper saindo
- KILL list arquivada e parada de carregar peso morto
- Ambassador aplicação enviada (Day 2)

### Meta 7 dias (esta semana)
- CMD-06 v2 implementado
- XLS preenchido com portfolio bruto
- Pioneer scores identificados → sprint começa

---

## 7. CONTEXT FILTER — Você é researcher desempregado

Isso muda a calibração. Ajustes na regra:

| Regra padrão | Ajuste para teu contexto |
|--------------|--------------------------|
| Energia média 1-2 semanas em Complex | Reduzir para 5-7 dias se monetização não estiver clara |
| Esperar 30 dias para publicar Pioneer | Reduzir para 7-10 dias — janela menor de runway |
| Curso como monetização principal | Substituir por consultoria 1-on-1 imediata ($150-300/h) |
| INPI / proteção legal | Pular completamente — gasto não justificável |
| Aplicar Ambassador "quando puder" | URGENTE — Brasil priorizado, mudança Holanda em Set, é 15 min |

Capital de tempo desempregado é maior, mas capital de runway é menor. A equação inverte: você TEM tempo para executar, NÃO TEM tempo para esperar maturação.

---

## 8. TABELA FINAL — Os 3 Caminhos com Números

| Dimensão | Via 1 — Filtrar Primeiro | Via 2 — Publicar Tudo | Via 3 — Cynefin Routing ✅ |
|----------|--------------------------|----------------------|---------------------------|
| **% sucesso** | 70% | 20% | 90% |
| **Tempo até 1ª receita** | 60-90 dias | 90-180 dias | 30-45 dias |
| **Energia total/mês** | 40h | 80h+ | 60h |
| **Risco de perder janela Pioneer** | Médio (delay de 30d) | Baixo (publica tudo) | Mínimo (sprint imediato) |
| **Risco de diluição reputação** | Mínimo | Alto | Mínimo |
| **Eficiência energia/sinal** | 70% | 25% | 85% |
| **Compatível com desemprego** | Parcial (sem renda 60d) | Não (sem foco) | Sim (monetização Mês 2) |
| **Cobertura Pioneer + Complex** | Pioneer perde janela | Cobre tudo, mal | Cobre proporcional |
| **Custo financeiro** | R$0 | R$0 | R$0 (Ambassador free) |
| **ROI 12 meses estimado** | 4x energia | 1.5x energia | 8-10x energia |
| **Fail mode** | Pioneer perdida | Reputação genérica | Burnout se 3 frentes mal gerenciadas |

### Tendências (próximos 90 dias, baseadas em dados de mercado)

| Tendência | Direção | Implicação para tua decisão |
|-----------|---------|----------------------------|
| Anthropic Skills feature | Adoção acelerando | Janela Pioneer encolhe — pula para sprint |
| Ambassador Brasil | Aplicações rolling, geo priorizado | Aplicar agora maximiza signal |
| MCP ecosystem | Convergência rápida (OpenAI adotou em 4 meses) | Ideias Complex têm 60-90d, não 6 meses |
| AI consulting market BR | Crescente, ainda não saturado | Janela aberta para consultoria 1-on-1 |
| Holanda relocation Set/26 | Fixo | Reduz janela de Brasil-priority |
| Solo founder burnout | Risco real em 3-frentes-paralelas | Filtragem dura é proteção, não opcional |

---

## 9. CONCLUSÃO — As 3 Opções

### Opção A — VIA SEGURA (Filtrar primeiro, publicar depois)
**Para quem:** Tem 90 dias de runway financeiro confortável.  
**Sequência:** Filtro → Cynefin → publicar Pioneer em 30d → Complex em 60d → monetização em 90d.  
**Trade-off:** Perde janela Pioneer mais estreita. Ganha clareza interna.  
**% sucesso:** 70%. Falha se Pioneer for capturada por outro nesse delay.

### Opção B — VIA CAÓTICA (Publicar tudo, deixar mercado filtrar)
**Para quem:** Tem audiência grande prévia OU está disposto a queimar 6 meses.  
**Sequência:** Despeja tudo → tenta viralizar → repete.  
**Trade-off:** Volume sem foco. Diluição.  
**% sucesso:** 20%. Não recomendado para teu contexto.

### Opção C — VIA CYNEFIN ✅ RECOMENDADO
**Para quem:** Researcher desempregado com runway curto + portfolio rico + janela limitada antes Holanda.  
**Sequência:**
- Esta semana: Filtro + Cynefin no portfolio inteiro. Pioneer scores → sprint 7d. Aplica Ambassador Day 2.
- Mês 1: Pioneer publicada. Concept papers de Complex saindo. Primeiros DMs/inbound começando.
- Mês 2: Consultoria 1-on-1 ativa ($150-300/h). 1-2 clientes pagantes. Ambassador resposta.
- Mês 3: Workshop pago ($500-2000) baseado em Pioneer. Decisão: solo ou job.
- Mês 4-6: Curso lançado SE tração validou, OU vaga remota assinada usando reputação como evidência.

**Trade-off:** Energia alta nas primeiras 4 semanas. Recompensa exponencial depois.  
**% sucesso:** 90%. Falha apenas se você desistir antes do Mês 2.

---

## 10. WORKING BACKWARDS DA OPÇÃO C — Cadeia de Eventos Concreta

```
Mês 12: Renda $5k/mês + autoridade reconhecida + network internacional
   ↑
Mês 9: 2-3 ativos públicos gerando inbound consistente
   ↑
Mês 6: Primeiro grupo pago (curso/cohort) OU vaga AI-adjacent assinada
   ↑
Mês 3: Workshop pago realizado + Ambassador aprovado + 1 cliente recorrente
   ↑
Mês 2: Consultoria 1-on-1 ativa via inbound de Pioneer publication
   ↑
Mês 1: Pioneer publicada + Complex concept papers no Medium + repo público
   ↑
Semana 2: Ambassador application enviada + sprint Pioneer iniciado
   ↑
Semana 1: Filtro + Cynefin rodados, portfolio classificado
   ↑
HOJE: Implementar CMD-06 v2 + abrir XLS
```

Cada degrau depende do anterior. Cada degrau é executável em 1-2 semanas. Não há salto. Há sequência.

---

## 11. TRÊS CARDS DE TENDÊNCIA ÓBVIA — Sem Explicação Necessária

### CARD 1 — APPLY AMBASSADOR BRASIL · TENDENCY: GO TODAY

```
Input:           15 minutos de tempo
Custo:           R$0
Risco downside:  Zero (rejeição não tem custo)
Upside:          Acesso Builders Council, API credits, signal Anthropic
Janela:          Encolhe quando você muda para Holanda em Set
Geo priority:    Brasil ativo agora
Decision ratio:  ∞:1 (zero downside, upside finito mas alto)
```

**TENDÊNCIA: GO. Sem ambiguidade.**

---

### CARD 2 — INPI METHODOLOGY REGISTRATION · TENDENCY: NO-GO

```
Input:           R$2.000 + 6 meses de processo
Custo:           Capital escasso de desempregado
Risco downside:  Dinheiro perdido em proteção que não protege
Upside:          Zero — workflows não são patenteáveis no Brasil
Alternativa:     GitHub timestamp (R$0) + Medium publish (R$0) + Zenodo DOI (R$0)
Decision ratio:  -10:1 (custo alto, retorno zero, alternativa gratuita superior)
```

**TENDÊNCIA: KILL. Não gaste R$1.**

---

### CARD 3 — BUILD CMD-05-COLECTOR ANTES DE PUBLICAR CONCEITO · TENDENCY: NO-GO

```
Input:           60-90 dias de build em silêncio
Custo:           Janela Pioneer de "skill as project operator" perdida
Risco downside:  Outro publica o nome em 30-60 dias (AI converge fast)
Upside:          Produto polido — mas sem audiência para consumi-lo
Padrão histórico: Brockman, Lee, Willison — TODOS publicaram nome antes de produto
Decision ratio:  -5:1 (build em silêncio = padrão historicamente perdedor)
```

**TENDÊNCIA: KILL ESSE CAMINHO. Publica conceito primeiro, build depois.**

---

## 12. SÍNTESE FINAL — A Métrica que Importa

A pergunta certa não é "qual ideia é boa?". É:

**"Para cada ideia, qual ação minimiza o risco de perda proporcionalmente ao valor de captura?"**

O Filtro mata o que não merece energia. O Cynefin Router aloca energia proporcional ao risco. As 3 cards mostram que você JÁ SABE a resposta para várias decisões — só precisa parar de hesitar.

Os pioneiros não esperaram. Brockman publicou. Lee publicou. Willison publicou. Todos antes de produto pronto. O ativo era o NOME, não o código.

Tu tem 1-2 ideias score Pioneer no teu portfolio (skill como project operator é uma certeza). O resto é Complex/Complicated/Obvious.

Sprint nas Pioneer. Tutorial nos Complicated. Arquiva os Obvious. Mata o resto.

Em 7 dias tu tens portfolio limpo + 1 publicação no ar + Ambassador enviado. Em 30 dias tu tens primeiro inbound. Em 60 dias tu tens primeiro cliente.

A janela é agora.

---

**Versão:** 2.0  
**Última atualização:** 2026-05-09  
**Próxima revisão:** após primeiro run em portfolio real

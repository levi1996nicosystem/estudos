# Exemplos Realistas de Cálculo — ICMS, ICMS-ST, DIFAL, IPI, PIS e COFINS

> Todos os NCMs, alíquotas de IPI e situações de ST/exclusão de ST citados aqui foram confirmados em fontes reais (TIPI, RICMS/SP, Portarias SRE) em agosto/2026. Alíquotas de ICMS interno/interestadual, PIS/COFINS de venda e o MVA/IVA-ST do exemplo 2 são **valores didáticos e devem ser confirmados** na legislação vigente antes de usar em produção — eles mudam com frequência.

---

## EXEMPLO 1 — Furadeira elétrica (NCM 8467.21.00)

**Por que esse produto é um bom exemplo:** é uma mercadoria comum em ERPs de ferramentaria/varejo, tem IPI real e confirmado (5,2%), e — ponto importante para aprender — **está expressamente excluída do regime de ICMS-ST em São Paulo**, mesmo fazendo parte de uma família de produtos (ferramentas com motor elétrico) que tem ST para peças e acessórios. Isso mostra que o ST se define **NCM por NCM**, nunca por "categoria".

**Alíquota de IPI confirmada na TIPI:** 5,2%
**Regras usadas:** ICMS interno SP = 18% | ICMS interno MG = 18% | ICMS interestadual SP→MG = 12% | PIS 1,65% / COFINS 7,6% (regime não-cumulativo, didático) | FCP-MG = 2%

**Dados do item (iguais nos 3 cenários):**

| Qtde | Preço Unit. | Subtotal | Frete | Seguro | Outras Desp. | Desconto | Total do Item |
|---|---|---|---|---|---|---|---|
| 10 | R$ 200,00 | R$ 2.000,00 | R$ 100,00 | R$ 20,00 | R$ 30,00 | R$ 50,00 | **R$ 2.100,00** |

### Cenário 1.1 — Venda interna SP → SP (revenda, comprador contribuinte)

| Qtde | Preço | Subtotal | Frete | Seguro | Outras Desp. | Desconto | Total Item | ICMS (próprio) | IPI | PIS | COFINS | ICMS-ST | DIFAL | **Total Geral** |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 10 | 200,00 | 2.000,00 | 100,00 | 20,00 | 30,00 | 50,00 | 2.100,00 | 378,00 (destacado) | 109,20 | 34,65 (destacado) | 159,60 (destacado) | — | — | **2.209,20** |

Cálculo: IPI = 2.100 × 5,2% = 109,20 · ICMS = 2.100 × 18% = 378,00 · Total = 2.100 + 109,20 (só o IPI soma)

### Cenário 1.2 — Venda interestadual SP → MG (revenda, comprador contribuinte)

| Qtde | Preço | Subtotal | Frete | Seguro | Outras Desp. | Desconto | Total Item | ICMS (próprio) | IPI | PIS | COFINS | ICMS-ST | DIFAL | **Total Geral** |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 10 | 200,00 | 2.000,00 | 100,00 | 20,00 | 30,00 | 50,00 | 2.100,00 | 252,00 (destacado) | 109,20 | 34,65 (destacado) | 159,60 (destacado) | — | — | **2.209,20** |

Cálculo: ICMS = 2.100 × 12% (alíquota interestadual) = 252,00. **Total idêntico ao Cenário 1.1** — só muda quem fica com o ICMS (SP recebe 252,00 em vez de 378,00). Sem DIFAL porque o comprador é contribuinte/revenda.

### Cenário 1.3 — Venda interestadual SP → MG, para consumidor final (pessoa física) → aparece o DIFAL

| Qtde | Preço | Subtotal | Frete | Seguro | Outras Desp. | Desconto | Total Item | ICMS (próprio) | IPI | PIS | COFINS | ICMS-ST | DIFAL + FCP | **Total Geral** |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 10 | 200,00 | 2.000,00 | 100,00 | 20,00 | 30,00 | 50,00 | 2.100,00 | 252,00 (destacado) | 109,20 | 34,65 (destacado) | 159,60 (destacado) | — | 126,00 + 42,00 | **2.377,20** |

Cálculo: DIFAL = 2.100 × (18% − 12%) = 126,00 · FCP = 2.100 × 2% = 42,00 · Total = 2.100 + 109,20 + 126,00 + 42,00 = **2.377,20**

---

## EXEMPLO 2 — Tinta látex (NCM 3210.00.10)

**Por que esse produto é um bom exemplo:** tem IPI real e confirmado (6,5%), possui CEST próprio (24.001.00) e **está de fato sujeita ao ICMS-ST em São Paulo**, o que permite ver a fórmula completa do ST na prática — algo que o Exemplo 1 não permitia.

⚠️ **Nota de estudo importante:** o percentual de MVA/IVA-ST de tintas em SP é definido por Portaria SRE específica e muda com frequência (a mais recente válida encontrada cobre 01/11/2024 a 31/07/2027, mas o segmento inteiro de tintas está previsto para **sair da ST em SP a partir de 01/10/2026**, conforme reestruturação do regime). Por isso, uso aqui um **MVA ilustrativo de 35%** só para você entender a mecânica da fórmula — **nunca use esse número em uma nota fiscal real**; sempre confirme o MVA vigente na Portaria CAT/SRE do estado de destino.

**Alíquota de IPI confirmada na TIPI:** 6,5%
**Regras usadas:** ICMS interno SP = 18% | ICMS interestadual SP→MG = 12% | MVA-ST = 35% (**ilustrativo**) | PIS 1,65% / COFINS 7,6%

**Dados do item:**

| Qtde | Preço Unit. | Subtotal | Frete | Seguro | Outras Desp. | Desconto | Total do Item |
|---|---|---|---|---|---|---|---|
| 20 | R$ 80,00 | R$ 1.600,00 | R$ 60,00 | R$ 10,00 | R$ 20,00 | R$ 30,00 | **R$ 1.660,00** |

### Cenário 2.1 — Venda interna SP → SP (fabricante vende para revenda, é o "substituto tributário")

| Qtde | Preço | Subtotal | Frete | Seguro | Outras Desp. | Desconto | Total Item | ICMS (próprio) | IPI | PIS | COFINS | ICMS-ST | DIFAL | **Total Geral** |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 20 | 80,00 | 1.600,00 | 60,00 | 10,00 | 20,00 | 30,00 | 1.660,00 | 298,80 (destacado) | 107,90 | 27,39 (destacado) | 126,16 (destacado) | **130,80** | — | **1.898,70** |

**Passo a passo do ICMS-ST:**
1. IPI = 1.660,00 × 6,5% = **107,90**
2. Base ST = (Total Item + IPI) × (1 + MVA) = (1.660,00 + 107,90) × 1,35 = 1.767,90 × 1,35 = **2.386,67**
3. ICMS cheio sobre a Base ST = 2.386,67 × 18% = **429,60**
4. ICMS próprio da operação = 1.660,00 × 18% = **298,80**
5. ICMS-ST a recolher = 429,60 − 298,80 = **130,80**
6. Total Geral = 1.660,00 + 107,90 (IPI) + 130,80 (ST) = **R$ 1.898,70**

📌 Note que, com ST, o comprador **não precisa mais recolher ICMS nenhum** nas próximas vendas desse mesmo produto — o valor já cobre a cadeia inteira até o consumidor final. É por isso que **não existe DIFAL** nesse cenário, mesmo numa venda futura interestadual: o ST já "resolveu" a repartição entre estados.

### Cenário 2.2 — Mesma operação, mas interestadual SP → MG (fabricante substituto tributário, por convênio/protocolo entre os estados)

| Qtde | Preço | Subtotal | Frete | Seguro | Outras Desp. | Desconto | Total Item | ICMS (próprio) | IPI | PIS | COFINS | ICMS-ST | DIFAL | **Total Geral** |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 20 | 80,00 | 1.600,00 | 60,00 | 10,00 | 20,00 | 30,00 | 1.660,00 | 199,20 (destacado) | 107,90 | 27,39 (destacado) | 126,16 (destacado) | **230,40** | — | **1.998,30** |

**Passo a passo:**
1. ICMS próprio = 1.660,00 × 12% (interestadual) = **199,20**
2. Base ST (mesma do Cenário 2.1) = 2.386,67
3. ICMS cheio sobre a Base ST (18%, alíquota interna de MG) = 2.386,67 × 18% = **429,60**
4. ICMS-ST = 429,60 − 199,20 = **230,40**
5. Total Geral = 1.660,00 + 107,90 (IPI) + 230,40 (ST) = **R$ 1.998,30**

Note que o ICMS-ST ficou **maior** que no Cenário 2.1 (230,40 vs. 130,80) — isso faz sentido: como o ICMS próprio da operação interestadual (12%) é menor que o interno (18%), a "sobra" que o ST precisa cobrir para chegar até a alíquota cheia de MG é maior.

*(Nota: quando a operação é interestadual, muitos estados exigem o "MVA ajustado" — uma fórmula que recalcula o MVA original para compensar a diferença entre a alíquota interestadual e a interna do estado de destino, como vimos no artigo do RICMS/SP sobre esse tema. Por simplicidade didática, usei aqui o MVA original sem ajuste; na prática, sempre confirme se o estado de destino exige esse ajuste.)*

---

## Por que PIS e COFINS não mudam entre os exemplos acima

Note que, nos dois produtos, usei sempre **1,65% e 7,6%** — isso porque PIS/COFINS não dependem do NCM nem do estado, e sim do **regime tributário da empresa vendedora**. Veja como o mesmo item mudaria só trocando o regime:

| Regime da empresa vendedora | PIS | COFINS | Sobre R$ 1.660,00 (Exemplo 2) |
|---|---|---|---|
| Lucro Real (não-cumulativo) | 1,65% | 7,6% | PIS R$ 27,39 + COFINS R$ 126,16 |
| Lucro Presumido (cumulativo) | 0,65% | 3% | PIS R$ 10,79 + COFINS R$ 49,80 |
| Simples Nacional | — | — | Já embutido numa alíquota única do DAS; não aparece destacado assim na nota |

---

## Resumo comparativo dos 5 cenários

| Cenário | Total Item | IPI | ICMS-ST | DIFAL+FCP | **Total Geral** |
|---|---|---|---|---|---|
| 1.1 Furadeira SP→SP revenda | 2.100,00 | 109,20 | — | — | **2.209,20** |
| 1.2 Furadeira SP→MG revenda | 2.100,00 | 109,20 | — | — | **2.209,20** |
| 1.3 Furadeira SP→MG consumidor final | 2.100,00 | 109,20 | — | 168,00 | **2.377,20** |
| 2.1 Tinta SP→SP com ST | 1.660,00 | 107,90 | 130,80 | — | **1.898,70** |
| 2.2 Tinta SP→MG com ST | 1.660,00 | 107,90 | 230,40 | — | **1.998,30** |

**A lição central dos dois exemplos:** o que soma ao Total Geral da nota é sempre **IPI + (ICMS-ST OU DIFAL, nunca os dois)**. O ICMS "normal" nunca soma — ele é só destacado para controle e crédito fiscal.

---

*Fontes consultadas: TIPI (Receita Federal, dados de 2026), RICMS/SP (art. 313-Z11, sobre exclusão de furadeiras elétricas da ST), Portarias SRE/CAT sobre IVA-ST de tintas e vernizes e reestruturação da ST em SP para 2026. Alíquotas de ICMS interno/interestadual e MVA usados nos cálculos são ilustrativos onde indicado — sempre confirme os valores vigentes antes de aplicar em um sistema real.*

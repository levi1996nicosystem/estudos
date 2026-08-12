# Guia de Referência — ICMS, ICMS-ST, DIFAL, IPI, PIS e COFINS

> Guia rápido para consulta no dia a dia. Para cada imposto: **o que é** → **fórmula** → **observação prática**.

---

## 1. ICMS (o "imposto-mãe")

**O que é:** imposto **estadual** sobre circulação de mercadorias. Calculado **"por dentro"** — já vem embutido no preço, não soma ao total da nota.

**Fórmula:**

```
ICMS = Base de Cálculo × Alíquota
```

- Base de cálculo = valor da mercadoria + frete/seguro/despesas acessórias (quando cobrados pelo vendedor), geralmente **incluindo o IPI** quando a venda é para uso/consumo do comprador (não para revenda).
- Alíquota varia conforme: estado de origem, estado de destino, e se a operação é interna ou interestadual (4%, 7% ou 12% interestadual; 17% a 22% interna, dependendo do estado).

**Observação prática:** não soma ao total da nota — é só destacado para fins de crédito/informação fiscal.

---

## 2. ICMS-ST (Substituição Tributária)

**O que é:** **não é um imposto novo** — é o próprio ICMS, cobrado **antecipadamente, de uma vez, por um responsável na cadeia** (geralmente o fabricante/importador), em vez de cada empresa recolher na sua etapa. Só existe para produtos listados especificamente em lei (por NCM).

**Fórmula:**

```
Base ST = (Total do Item + IPI) × (1 + MVA)
ICMS-ST = (Base ST × Alíquota interna do destino) − ICMS próprio da operação
```

- MVA (Margem de Valor Agregado) = percentual definido por estado/produto, que estima a margem de lucro do resto da cadeia.
- **Soma ao total da nota** (o comprador paga o ST junto).

**Observação prática:** quando o produto tem ST, a cadeia toda de ICMS até o consumidor final já foi "resolvida" ali. Por isso ST e DIFAL nunca aparecem juntos no mesmo item. O ST é definido **NCM por NCM** — produtos parecidos podem ter tratamentos diferentes, então sempre confirme na legislação vigente do estado de destino (Portaria CAT, Convênio ICMS, etc.), nunca por "categoria" do produto.

---

## 3. DIFAL (Diferencial de Alíquota)

**O que é:** também não é imposto novo — é **ICMS complementar**. Só existe em venda **interestadual para consumidor final** (não contribuinte de ICMS). Serve para garantir que o estado de destino receba a diferença entre sua alíquota interna e a interestadual usada na operação.

**Fórmula:**

```
DIFAL = (Alíquota interna do destino − Alíquota interestadual) × Base
FCP   = Base × Alíquota do FCP (definida pelo estado de destino)
```

- FCP (Fundo de Combate à Pobreza) pode ser cobrado por cima do DIFAL, dependendo do estado de destino.

**Observação prática:** **soma ao total da nota**. Só se aplica quando NÃO há ST no item e a venda é para consumidor final fora do estado de origem.

---

## 4. IPI (Imposto sobre Produtos Industrializados)

**O que é:** imposto **federal**, incide sobre produtos industrializados na saída do estabelecimento industrial (ou na importação). Calculado **"por fora"** — soma ao total da nota.

**Fórmula:**

```
IPI = Base de Cálculo × Alíquota
```

- Base = valor do produto + frete/seguro/despesas acessórias cobradas pelo vendedor (desconto incondicional reduz a base).
- Alíquota vem da **TIPI**, indexada pelo **NCM** do produto — varia de 0% a mais de 300% (ex: cigarros), mas a maioria dos produtos fica entre 0% e ~20%.

**Observação prática:** é federal — não muda por estado de origem/destino, só muda por produto (NCM).

---

## 5. PIS e COFINS

**O que são:** contribuições **federais** que incidem sobre o faturamento/receita da empresa vendedora. Calculadas **"por dentro"** — não somam ao total da nota (assim como o ICMS).

**Fórmula (regime não-cumulativo — comum em Lucro Real):**

```
PIS     = Base de Cálculo × 1,65%
COFINS  = Base de Cálculo × 7,6%
```

**Fórmula (regime cumulativo — comum em Lucro Presumido):**

```
PIS     = Base de Cálculo × 0,65%
COFINS  = Base de Cálculo × 3%
```

- Base = normalmente o valor da mercadoria (com pequenas exclusões, dependendo do regime).
- Existe também **PIS/COFINS-Importação**, com alíquotas diferentes — não confundir com as alíquotas de venda interna.

**Observação prática:** são os únicos dois impostos desta lista que **não dependem do NCM nem do estado** — dependem do **regime tributário da empresa vendedora** (Lucro Real × Lucro Presumido × Simples Nacional). No Simples Nacional, PIS e COFINS já vêm embutidos numa alíquota única do DAS e não aparecem destacados dessa forma na nota.

---

## Tabela-resumo (a "chave" de tudo)

| Imposto   | Esfera    | Depende de                              | Por dentro ou por fora? | Soma ao Total da Nota? |
|-----------|-----------|------------------------------------------|--------------------------|--------------------------|
| ICMS      | Estadual  | Estado origem/destino                    | Por dentro               | ❌ Não |
| ICMS-ST   | Estadual  | NCM do produto + estado destino          | Por dentro (embutido)    | ✅ Sim |
| DIFAL     | Estadual  | Estado destino + tipo de comprador       | —                         | ✅ Sim |
| IPI       | Federal   | NCM do produto                           | Por fora                 | ✅ Sim |
| PIS       | Federal   | Regime tributário da empresa             | Por dentro               | ❌ Não |
| COFINS    | Federal   | Regime tributário da empresa             | Por dentro               | ❌ Não |

---

## Ordem lógica de cálculo numa NF-e

```
Subtotal (Qtde × Preço)
  + Frete + Seguro + Outras Despesas
  − Desconto
  = TOTAL DO ITEM
      ↓
   [IPI]  → sobre o Total do Item
      ↓
   [ICMS] → sobre o Total do Item (às vezes + IPI, depende do caso)
      ↓
   [PIS/COFINS] → sobre o Total do Item
      ↓
   [ICMS-ST ou DIFAL] → nunca os dois juntos no mesmo item
```

---

*Guia elaborado com base em conceitos gerais de tributação sobre circulação de mercadorias. Alíquotas de ICMS, MVA/IVA-ST e regras específicas variam por estado, produto (NCM) e legislação vigente — sempre confirme na fonte oficial (RICMS do estado, Portaria CAT, TIPI da Receita Federal) antes de aplicar em produção.*

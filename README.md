# 📊 Ju-Invest — Simulador e Dashboard de Alocação em FIIs

> Um dashboard interativo em Excel com design de aplicativo, desenvolvido para responder às 5 principais perguntas de planejamento financeiro antes de investir em Fundos de Investimento Imobiliário (FIIs), completo com projeção de cenários, alocação automatizada de carteira por perfil de risco e simulação baseada na regra de 30% da renda.

## 📌 Visão Geral

A planilha **Ju-Invest** funciona como um painel de controle financeiro dinâmico que transforma premissas básicas de investimento em análises práticas e visuais. Desenvolvida com uma interface moderna no estilo aplicativo (linhas de grade ocultas, diferenciação clara entre células de entrada e saída, e indicadores visuais), ela oferece uma análise completa do acúmulo de patrimônio a longo prazo e da geração de renda passiva mensal.

---

## 🌟 Diferencial Competitivo: Aporte Sugerido (30% do Salário)

Enquanto a ferramenta padrão apresentada pelo *expert* calcula as projeções e distribuições estritamente a partir de um valor estático e manual de aporte mensal, o **Ju-Invest** traz uma **camada adicional de simulação e inteligência financeira**.

Foram inseridas **3 novas tabelas dinâmicas** e **1 novo gráfico visual** focado na aplicação da **Regra dos 30%**, onde a planilha calcula automaticamente a sugestão ideal de investimento com base no salário bruto/líquido informado (`=Salário * 0,30`). 

Essa melhoria permite ao investidor:
1. Comparar instantaneamente o seu aporte atual desejado contra o aporte recomendado pela regra de planejamento financeiro.
2. Visualizar como a adesão à meta de 30% de aporte impacta no acúmulo do patrimônio futuro e na aceleração da independência financeira.
3. Analisar a distribuição por FIIs proporcionalmente calibrada para essa renda de 30%.

---

## 🧮 Detalhamento Tabela por Tabela

### 1. **Configurações Globais (Painel de Entradas)**
* **Objetivo:** Atuar como o centro de controle dos parâmetros individuais do investidor.
* **Entradas e Cálculos Dinâmicos:**
  * **Salário Mensal (R\$):** Valor de entrada da renda mensal do usuário.
  * **Rendimento da Carteira (% a.m.):** Taxa de retorno mensal esperada.
  * **Sugestão de Aporte (30%):** Calcula automaticamente $30\%$ do salário mensal (`=Salário * 0,30`).
  * **Aporte Efetivo (R\$):** Valor do aporte mensal efetivamente escolhido para os cálculos manuais.
  * **Prazo (Anos):** Horizonte de tempo pretendido para o investimento.
* **Intervalos Nomeados Utilizados:** `aporte`, `anos`, `taxa_mensal`, `perfil`, `salario`.

---

### 2. **Perguntas de Negócio (Painel KPI Principal)**
* **Objetivo:** Responder de forma direta e rápida às 5 perguntas essenciais de negócio no topo do dashboard com base no aporte efetivo escolhido.
* **Indicadores Calculados:**
  1. **Quanto investir por mês:** Exibe o valor do aporte mensal definido (`aporte`).
  2. **Por quantos anos:** Exibe o prazo total em anos (`anos`).
  3. **Taxa de rendimento mensal:** Exibe a taxa de juros informada (`taxa_mensal`).
  4. **Patrimônio Acumulado:** Total acumulado ao final do período, utilizando a função `VF`.
  5. **Dividendos Mensais:** Renda passiva estimada gerada por mês a partir do patrimônio acumulado.

---

### 3. **Projeção de Cenários — Aporte Atual Efetivo**
* **Objetivo:** Comparar a evolução do patrimônio e dos dividendos em horizontes fixos de **2, 5, 10, 20 e 30 anos**.
* **Colunas da Tabela:**
  * **Horizonte (Anos):** Período de projeção em anos.
  * **Meses (nper):** Converte o período em quantidade total de meses/períodos de capitalização ($\text{Anos} \times 12$).
  * **Total Aportado (R\$):** Soma dos valores investidos do próprio bolso ($\text{Aporte Mensal} \times \text{Meses}$).
  * **Juros Compostos (R\$):** Ganho líquido gerado pela ação dos juros compostos ($\text{Patrimônio Acumulado} - \text{Total Aportado}$).
  * **Patrimônio Acumulado (R\$):** Valor futuro acumulado calculado dinamicamente para cada período via `VF`.
  * **Renda Mensal Estimada (R\$):** Dividendos mensais projetados a partir do patrimônio de cada cenário.

---

### 4. **Alocação de FIIs por Perfil — Aporte Atual**
* **Objetivo:** Dividir o aporte mensal efetivo entre 6 categorias de Fundos Imobiliários de acordo com o perfil de risco selecionado (**Conservador**, **Moderado** ou **Agressivo**).
* **Categorias de FIIs Incluídas:**
  * *Tijolo - Logística*
  * *Tijolo - Lajes Corporativas*
  * *Tijolo - Shopping Centers*
  * *Papel - CRIs*
  * *FOFs (Fundos de Fundos)*
  * *Outros / Fiagro / Desenvolvimento*
* **Colunas da Tabela:**
  * **% Alocação:** Porcentagem recuperada dinamicamente da aba de apoio conforme o perfil escolhido.
  * **Aporte Mensal (R\$):** Valor do aporte direcionado à categoria ($\% \text{ Alocação} \times \text{Aporte Total}$).
  * **Renda Mensal Estimada (R\$):** Estimativa de dividendos gerados especificamente por aquele segmento.

---

### 5. 🆕 **Módulo Adicional: Simulação com Sugestão de 30% do Salário**

Abaixo das tabelas principais, a versão **Ju-Invest 2** incorpora um módulo completo de simulação focado na meta de **30% do Salário**:

1. **Nova Tabela 1: Resposta das 5 Perguntas no Cenário 30%**
   * Recalcula imediatamente os KPIs essenciais de negócio (Patrimônio e Dividendos Mensais) substituindo o aporte manual pelo aporte equivalente a $30\%$ do salário do usuário.
2. **Nova Tabela 2: Projeção de Cenários (2 a 30 Anos com 30% de Aporte)**
   * Apresenta uma linha do tempo comparativa que demonstra o salto patrimonial alcançado no longo prazo ao manter $30\%$ da renda comprometida com os investimentos.
3. **Nova Tabela 3: Alocação de FIIs do Aporte Sugerido (30%)**
   * Reorganiza os valores em Reais ($R\$) destinados a cada um dos 6 tipos de FIIs considerando o montante total dos $30\%$ do salário.
4. **🆕 Novo Gráfico Visual:**
   * Gráfico de Rosca/Pizza dedicado exclusivamente para ilustrar a **Distribuição do Aporte Sugerido de 30% por Categoria de FII**, facilitando a visualização gráfica da nova meta de alocação.

---

### 6. **Matriz de Apoio (Aba `Apoio` ou `Planilha2`)**
* **Objetivo:** Servir como base de dados auxiliar contendo a matriz cruzada entre perfis de risco, categorias de fundos, chave composta e percentuais de distribuição.

---

## 📐 Explicação Detalhada das Fórmulas

### 1. `VF` (Valor Futuro)
A função `VF` calcula o valor futuro de um investimento com base em pagamentos periódicos e constantes a uma taxa de juros fixa (juros compostos).

#### **Sintaxe no Excel:**
```excel
=VF(taxa; nper; pgto; [vp]; [tipo])
```

#### **Parâmetros Explicados:**
* **`taxa` (`taxa_mensal`):** Taxa de juros aplicada por período (ex: $1,08\% = 0,0108$).
* **`nper` (`anos * 12`):** Número total de períodos/meses de aplicação.
* **`pgto` (`-aporte`):** O valor do aporte mensal constante. **Observação:** É passado com sinal negativo (`-`) porque representa uma saída de caixa, garantindo que o resultado retorne como um valor patrimonial positivo.
* **`[vp]` (0 ou omitido):** Valor presente/inicial. Definido como $0$, assumindo que o investimento começa do zero.
* **`[tipo]` (0):** Pagamentos efetuados no final do período.

#### **Equação Matemática Equivalente:**
$$VF = \text{Aporte} \times \left( \frac{(1 + i)^n - 1}{i} \right)$$
*Onde* $i = \text{taxa\_mensal}$ *e* $n = \text{total de meses}$.

---

### 2. `PROCV` (Procura Vertical)
A função `PROCV` busca um determinado valor na primeira coluna de uma tabela e retorna o valor correspondente na mesma linha de uma coluna especificada.

#### **Sintaxe no Excel:**
```excel
=PROCV(valor_procurado; matriz_tabela; indice_coluna; [procurar_intervalo])
```

#### **Aplicação no Ju-Invest (Busca por Chave Composta):**
Como a porcentagem de alocação depende de **dois critérios simultâneos** (Perfil de Risco + Tipo de FII), foi criada uma **Chave Composta** concatenando ambos os valores com o caractere de ligação `_`:

```excel
=PROCV(perfil & "_" & C39; Apoio!$A$2:$D$19; 4; FALSO)
```

#### **Detalhamento dos Parâmetros:**
1. **`valor_procurado` (`perfil & "_" & C39`):** Une o perfil selecionado (ex: `"Moderado"`) com o nome do tipo de FII (ex: `"Tijolo - Logística"`), gerando a chave única `"Moderado_Tijolo - Logística"`.
2. **`matriz_tabela` (`Apoio!$A$2:$D$19`):** Intervalo da tabela de apoio onde a Coluna A contém a chave composta para busca.
3. **`indice_coluna` (`4`):** Indica ao Excel para retornar o valor contido na **4ª coluna** da tabela (onde estão localizadas as porcentagens de alocação).
4. **`[procurar_intervalo]` (`FALSO`):** Exige uma correspondência **exata** no momento da busca.

---

## 🚀 Recursos do Excel Utilizados

* **Design Estilo App (UX/UI):** Cores modernas, layout estruturado em blocos/cartões e remoção de linhas de grade.
* **Validação de Dados:** Lista suspensa (*dropdown*) para escolha dinâmica do perfil de risco (`Conservador`, `Moderado`, `Agressivo`).
* **Intervalos Nomeados:** Substituição de endereços de células por nomes explicativos como `aporte`, `anos`, `taxa_mensal`, `perfil` e `salario`.
* **Visualização Gráfica Dupla:** Gráficos interativos para acompanhar tanto o cenário do aporte livre quanto o cenário sugerido dos 30% da renda.

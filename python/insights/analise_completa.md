# 🔬 Análise Exploratória Profunda: Decifrando os Fatores de Turnover

Esta página documenta o processo de investigação e as principais descobertas da Análise Exploratória de Dados (EDA) realizada sobre o dataset "IBM HR Analytics". O objetivo desta etapa foi ir além dos dados brutos para encontrar os verdadeiros gatilhos que levam à saída de colaboradores.

Utilizando Python, com as bibliotecas Pandas para manipulação e Seaborn/Matplotlib para visualização, cada seção abaixo detalha uma pergunta de negócio, o gráfico gerado para respondê-la e os insights extraídos.

Estas descobertas serviram como o alicerce para a construção da lógica de "Score de Risco" no pipeline de automação e para o design do dashboard final no Power BI.

---

## 💎 Raio-X da Empresa 💎

![Histogramas](../graficos/histogramas_seaborn.png)

Análise dos histogramas de distribuição das variáveis numéricas do dataset.

***

### 👤 Perfil da Equipe: Madura e Experiente
* **Observação:** O gráfico de `Idade` mostra uma forte concentração de funcionários entre 30 e 40 anos, e o de `Anos de Carreira` tem seu pico em 10 anos.
* **O que isso significa?** A sua força de trabalho é **madura e experiente**, não sendo composta majoritariamente por recém-formados. O pico de 10 anos de experiência é um momento crítico na carreira, ideal para focar em estratégias de retenção para este grupo.

***

### 💰 A Estrutura Salarial: Uma Pirâmide Clássica
* **Observação:** O histograma de `Salário Mensal` é muito inclinado, com a maioria dos colaboradores nas faixas mais baixas (abaixo de $5.000).
* **O que isso significa?** É uma **estrutura de pirâmide** clássica. A progressão para altos salários é um funil bem estreito, o que pode ser um dos principais motivos para a saída de funcionários em busca de melhores oportunidades financeiras.

***

### ⏳ Tempo de Casa e Carreira Interna (O Insight Mais Forte!)
* **Observação:** Os gráficos de `Anos na Empresa`, `Anos no Cargo Atual` e, principalmente, `Anos desde a Última Promoção` são todos muito concentrados perto do zero.
* **O que isso significa?** Isso sugere fortemente uma **alta taxa de *turnover* (rotatividade)**. A hipótese é clara: se os funcionários não são promovidos nos primeiros anos, eles tendem a sair. A falta de um plano de carreira visível parece ser o maior problema da empresa.

***

### 😊 O Paradoxo da Satisfação
* **Observação:** A maioria dos funcionários se diz satisfeita (notas 3 e 4) em `Satisfação no Trabalho`, `Satisfação com Ambiente`, etc.
* **O que isso significa?** O insight não é que "todos estão felizes". O ponto-chave é o grupo que dá nota 1 (insatisfeito). Mesmo sendo minoria, **este é o grupo que deve ser investigado**, pois tem a maior probabilidade de sair da empresa.

***

### ⚠️ A Qualidade do Dado: A Avaliação Ineficaz
* **Observação:** O gráfico de `Nota de Performance` tem basicamente uma única barra, com quase todos os funcionários recebendo a mesma nota.
* **O que isso significa?** Como analista, você conclui que o sistema de avaliação de performance da empresa é ineficaz para diferenciar talentos. Portanto, esta coluna é **praticamente inútil para prever o *turnover***, o que já é um insight valioso sobre os processos de RH.

---

## 🏢 Distribuição por Departamento 🏢

Análise do gráfico de barras que mostra a composição da força de trabalho da empresa.

![Gráfico de Distribuição por Departamento](../graficos/barras_distribuicao_departamento.png)

***

### 🔬 Foco em Inovação e Produto
* **Observação:** O departamento de **P&D** é, de longe, o maior, com 961 colaboradores, mais que o dobro do time de Vendas (446).
* **O que isso significa?** O motor da empresa é a **criação e desenvolvimento de produtos**. Isso aponta para um setor de alta tecnologia, farmacêutico ou de biotecnologia, onde a vantagem competitiva está na inovação e não no volume da força de vendas.

***

### 📈 Vendas como Suporte Estratégico
* **Observação:** O time de Vendas é o segundo maior, mas com menos da metade do tamanho do P&D.
* **O que isso significa?** A estratégia de vendas provavelmente é focada em produtos de alto valor ou nicho de mercado, que demandam uma abordagem mais técnica e consultiva do que um grande volume de vendedores.

***

### ⚠️ Ponto Crítico: O Risco em Recursos Humanos
* **Observação:** O departamento de RH é extremamente enxuto (63 pessoas) para dar suporte a quase 1500 funcionários.
* **O que isso significa?** Este é um **risco operacional severo**. Uma equipe de RH potencialmente sobrecarregada pode ser um dos fatores ocultos que contribuem para o *turnover* geral, por ter dificuldades em gerenciar o desenvolvimento, o bem-estar e a retenção dos colaboradores de forma eficaz.




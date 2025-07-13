# 🔬 Análise Exploratória Profunda: Decifrando os Fatores de Turnover

Esta página documenta o processo de investigação e as principais descobertas da Análise Exploratória de Dados (EDA) realizada sobre o dataset "IBM HR Analytics". O objetivo desta etapa foi ir além dos dados brutos para encontrar os verdadeiros gatilhos que levam à saída de colaboradores.

Utilizando Python, com as bibliotecas Pandas para manipulação e Seaborn/Matplotlib para visualização, cada seção abaixo detalha uma pergunta de negócio, o gráfico gerado para respondê-la e os insights extraídos.

Estas descobertas serviram como o alicerce para a construção da lógica de "Score de Risco" no pipeline de automação e para o design do dashboard final no Power BI.

---

## 💎 Raio-X da Empresa 💎

![Histogramas](../graficos/histogramas_seaborn.png)

Análise dos histogramas de distribuição das variáveis numéricas do dataset.

### 👤 Perfil da Equipe: Madura e Experiente
* **Observação:** O gráfico de `Idade` mostra uma forte concentração de funcionários entre 30 e 40 anos, e o de `Anos de Carreira` tem seu pico em 10 anos.
* **O que isso significa?** A sua força de trabalho é **madura e experiente**, não sendo composta majoritariamente por recém-formados. O pico de 10 anos de experiência é um momento crítico na carreira, ideal para focar em estratégias de retenção para este grupo.

### 💰 A Estrutura Salarial: Uma Pirâmide Clássica
* **Observação:** O histograma de `Salário Mensal` é muito inclinado, com a maioria dos colaboradores nas faixas mais baixas (abaixo de $5.000).
* **O que isso significa?** É uma **estrutura de pirâmide** clássica. A progressão para altos salários é um funil bem estreito, o que pode ser um dos principais motivos para a saída de funcionários em busca de melhores oportunidades financeiras.

### ⏳ Tempo de Casa e Carreira Interna (O Insight Mais Forte!)
* **Observação:** Os gráficos de `Anos na Empresa`, `Anos no Cargo Atual` e, principalmente, `Anos desde a Última Promoção` são todos muito concentrados perto do zero.
* **O que isso significa?** Isso sugere fortemente uma **alta taxa de *turnover* (rotatividade)**. A hipótese é clara: se os funcionários não são promovidos nos primeiros anos, eles tendem a sair. A falta de um plano de carreira visível parece ser o maior problema da empresa.

### 😊 O Paradoxo da Satisfação
* **Observação:** A maioria dos funcionários se diz satisfeita (notas 3 e 4) em `Satisfação no Trabalho`, `Satisfação com Ambiente`, etc.
* **O que isso significa?** O insight não é que "todos estão felizes". O ponto-chave é o grupo que dá nota 1 (insatisfeito). Mesmo sendo minoria, **este é o grupo que deve ser investigado**, pois tem a maior probabilidade de sair da empresa.

### ⚠️ A Qualidade do Dado: A Avaliação Ineficaz
* **Observação:** O gráfico de `Nota de Performance` tem basicamente uma única barra, com quase todos os funcionários recebendo a mesma nota.
* **O que isso significa?** Como analista, você conclui que o sistema de avaliação de performance da empresa é ineficaz para diferenciar talentos. Portanto, esta coluna é **praticamente inútil para prever o *turnover***, o que já é um insight valioso sobre os processos de RH.

---

## 🏢 Distribuição por Departamento 🏢

Análise do gráfico de barras que mostra a composição da força de trabalho da empresa.

![Gráfico de Distribuição por Departamento](../graficos/barras_distribuicao_departamento.png)

### 🔬 Foco em Inovação e Produto
* **Observação:** O departamento de **P&D** é, de longe, o maior, com 961 colaboradores, mais que o dobro do time de Vendas (446).
* **O que isso significa?** O motor da empresa é a **criação e desenvolvimento de produtos**. Isso aponta para um setor de alta tecnologia, farmacêutico ou de biotecnologia, onde a vantagem competitiva está na inovação e não no volume da força de vendas.

### 📈 Vendas como Suporte Estratégico
* **Observação:** O time de Vendas é o segundo maior, mas com menos da metade do tamanho do P&D.
* **O que isso significa?** A estratégia de vendas provavelmente é focada em produtos de alto valor ou nicho de mercado, que demandam uma abordagem mais técnica e consultiva do que um grande volume de vendedores.

### ⚠️ Ponto Crítico: O Risco em Recursos Humanos
* **Observação:** O departamento de RH é extremamente enxuto (63 pessoas) para dar suporte a quase 1500 funcionários.
* **O que isso significa?** Este é um **risco operacional severo**. Uma equipe de RH potencialmente sobrecarregada pode ser um dos fatores ocultos que contribuem para o *turnover* geral, por ter dificuldades em gerenciar o desenvolvimento, o bem-estar e a retenção dos colaboradores de forma eficaz.

---

## 🎓 Formação Acadêmica da Equipe 🎓

Análise do gráfico de barras que detalha o perfil educacional dos colaboradores da empresa.

![Gráfico de Distribuição por Formação](../graficos/barras_distribuicao_formacao.png)

### 🔬 Perfil Científico Dominante (Confirmação da Hipótese)
* **Observação:** As duas formações mais comuns, **Ciências da Vida** (606) e **Medicina** (464), representam mais de 70% de toda a empresa.
* **O que isso significa?** Isso **confirma a identidade** da empresa como sendo do setor **farmacêutico ou de biotecnologia**. A expertise científica é, sem dúvida, o principal ativo da organização e a base que sustenta o gigantesco departamento de P&D.

### 📈 A Força Estratégica de Marketing
* **Observação:** "Marketing" é a terceira maior área de formação, com 159 colaboradores.
* **O que isso significa?** Estes profissionais provavelmente formam o núcleo estratégico do grande departamento de Vendas. Isso indica que a empresa não foca apenas em vender, mas em criar **estratégias de mercado sofisticadas** para seus produtos científicos, o que é essencial em setores de alta tecnologia.

### 🛠️ A Base Técnica e Operacional
* **Observação:** Existe um grupo considerável com **Curso Técnico** (132 pessoas).
* **O que isso significa?** Estes são os prováveis **técnicos de laboratório e especialistas operacionais** que dão o suporte prático à grande estrutura de P&D. O sucesso da inovação da empresa depende tanto deles quanto dos pesquisadores com formação superior.

### ⚠️ O Alerta do RH se Intensifica
* **Observação:** Apenas 27 funcionários têm formação em **Recursos Humanos**.
* **O que isso significa?** Este dado, combinado com o tamanho reduzido do departamento (que vimos no gráfico anterior), é um **alerta vermelho**. A equipe de RH não só é pequena para o tamanho da empresa, como também tem baixa especialização acadêmica na área, o que pode **intensificar os desafios de retenção** e gestão de talentos.

---

## 😊 Relação: Satisfação vs. Saída 😊

Análise do gráfico de barras que cruza o nível de satisfação no trabalho com a decisão do colaborador de ficar ou sair da empresa.

![Gráfico de Satisfação vs. Saída](../graficos/barras_satisfacao_vs_saida.png)

### 🔥 O Risco da Insatisfação em Números
* **Observação:** A **taxa de saída** para funcionários com satisfação nível 1 (Baixa) é de **22.8%** (66 de 289), enquanto para os de nível 4 (Muito Alta) é de apenas **11.3%** (52 de 459).
* **O que isso significa?** Um funcionário insatisfeito tem **mais que o dobro de chance** de deixar a empresa em comparação com um funcionário muito satisfeito. Este é o grupo mais volátil e que necessita de atenção imediata por parte do RH para evitar a perda de talentos.

### 💡 Por que os Satisfeitos Também Saem?
* **Observação:** O maior **número absoluto** de saídas (73 pessoas) vem do grupo com satisfação nível 3 ("Alto").
* **O que isso significa?** Isso prova que a satisfação, sozinha, não garante a retenção. Para este grupo, outros fatores, provavelmente ligados à **carreira (falta de promoção) e remuneração** (como vimos nos histogramas), são os gatilhos decisivos para a busca de novas oportunidades.

### ✨ A Barreira da "Super Satisfação"
* **Observação:** A taxa de saída cai significativamente do nível 3 (16.5%) para o nível 4 (11.3%).
* **O que isso significa?** Levar um funcionário de "satisfeito" para "muito satisfeito" cria uma **barreira de lealdade** real e mensurável. Investir em iniciativas que promovam um ambiente de trabalho excepcional pode ser uma estratégia de retenção tão importante quanto apenas "apagar incêndios" no grupo dos insatisfeitos.

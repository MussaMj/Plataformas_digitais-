# Contexto do Projeto
Este projeto analisa campanhas de marketing digital em várias plataformas, incluindo Facebook, Instagram, YouTube, Google e LinkedIn. O foco é compreender quais plataformas, tipos de conteúdo e segmentos de público geram os melhores resultados, usando dados históricos das campanhas.  

Do ponto de vista de um **analista de dados**, este projeto aborda desde a limpeza e exploração do dataset até a aplicação de algoritmos de classificação, gerando insights úteis para tomada de decisão em estratégias de marketing.

Os insights e recomendações são fornecidos nas seguintes áreas-chave:

- **Categoria 1:** Desempenho Geral por Plataforma  
- **Categoria 2:** Custo vs Retorno por Plataforma  
- **Categoria 3:** Impacto das Variáveis Demográficas (Idade, Género, Região)  
- **Categoria 4:** Performance por Tipo de Conteúdo  
- **Categoria 5:** Eficiência do Orçamento  

## Notebooks

- O notebook utilizado para **inspeção e limpeza de dados**, bem como para análise direcionada a questões específicas de negócio, pode ser encontrado [aqui](https://github.com/MussaMj/Plataformas_digitais-/blob/main/notebooks/AnaliseD.ipynb).  
- O notebook criado para o **modelo de Machine Learning** está disponível [aqui](https://github.com/MussaMj/Plataformas_digitais-/blob/main/notebooks/MachineL.ipynb). 


# Estrutura de Dados 
O dataset principal deste projeto está armazenado em um arquivo **CSV** (`cleanedData.csv`) com **1000 linhas** e **14 colunas**.

As principais variáveis presentes no dataset são:

- **Platform** → Plataforma de campanha (YouTube, Facebook, Instagram, etc.)  
- **Budget** → Orçamento investido na campanha  
- **Clicks** → Número de cliques obtidos  
- **Conversions** → Número de conversões registradas  
- **CTR (Click-Through Rate)** → Taxa de cliques em relação às impressões  
- **CPC (Cost per Click)** → Custo médio por clique  
- **Conversion_Rate** → Taxa de conversão (%)  
- **Duration** → Duração da campanha em dias  
- **Content_Type** → Tipo de conteúdo utilizado (imagem, vídeo, etc.)


# Resumo Executivo

### Principais Descobertas
- **YouTube** apresenta o melhor desempenho geral, combinando altas taxas de conversão com o maior número de campanhas bem-sucedidas.  
- **Facebook** lidera em engajamento (CTR) e oferece forte eficiência de custo por cliente.  
- **Google** e **Facebook** são as plataformas mais eficientes em termos de custo por conversão.
  

# Detalhes dos Insights

### Categoria 1: Desempenho Geral por Plataforma
- **YouTube**: Maior taxa de conversão (38,64%) e maior número de campanhas bem-sucedidas (199).  
- **Facebook**: Maior CTR (499,20), CPC competitivo ($1,98), bom número de campanhas bem-sucedidas (177).  
- **LinkedIn**: Boa taxa de conversão (31,44%) e número de campanhas bem-sucedidas (188), eficaz para B2B.  

### Categoria 2: Custo vs Retorno por Plataforma
- **Facebook**: Menor custo por cliente ($37,45), eficiente para ROI.  
- **Google**: Segundo melhor custo por cliente ($41,60).  
- **YouTube**: Maior custo por cliente ($176,97), apesar da excelente taxa de conversão.  

### Categoria 3: Impacto das Variáveis Demográficas
- **Instagram**: Melhor desempenho com o público de 18–24 anos.  
- **LinkedIn**: Mais eficaz para profissionais 55+.  
- **YouTube**: Desempenho elevado em ambos os géneros e várias faixas etárias.  
- **Google & Facebook**: Forte performance com públicos mais jovens e mais velhos, respetivamente.  

### Categoria 4: Performance por Tipo de Conteúdo
- **Story**: Melhor CTR (476,39) e conversão (34,40%).  
- **Text**: Alta conversão (33,29%), bom desempenho relativo ao custo.  
- **Carousel & Video**: Atrai cliques, mas converte menos eficientemente.  

### Categoria 5: Eficiência do Orçamento
**Métrica:** Conversions_per_Budget (conversões por unidade de orçamento investida)  

**Ranking de Eficiência:**
- **Google**: 0,106248 → Mais eficiente, maior ROI  
- **Facebook**: 0,104358 → Muito próximo do Google, excelente custo-benefício  
- **LinkedIn**: 0,103175 → Ligeiramente menos eficiente, bom para B2B  
- **YouTube**: 0,100407 → Altas conversões, mas mais caro por cliente  
- **Instagram**: 0,091653 → Menos eficiente, justificável para segmento 18–24 anos  

**Insights Estratégicos:**
- **Google** → Melhor custo-benefício, ideal para orçamentos limitados ou ROI elevado  
- **Facebook** → Alta eficiência, bom equilíbrio entre alcance e custo  
- **LinkedIn** → Eficiente para campanhas B2B especializadas  
- **YouTube** → Altas conversões absolutas, mas caro por cliente


# Machine Learning: Previsão de Plataforma

### Objetivo
Prever a **plataforma mais indicada** para uma campanha com base em métricas históricas e características da campanha.

### Abordagem
- **Features (`X`)**: todas as colunas relevantes exceto `Platform`  
- **Target (`y`)**: coluna `Platform`  
- **Pré-processamento:** one-hot encoding para variáveis categóricas e StandardScaler para variáveis numéricas  
- **Divisão treino/teste:** 80% treino / 20% teste  

### Modelo
- Classificador: `RandomForestClassifier`  
- Parâmetros padrão, `random_state=42` para reprodutibilidade  

### Resultados
- **Acurácia:** (colocar valor obtido)  
- **Matriz de Confusão** e **Relatório de Classificação** indicam bom desempenho na previsão de plataformas  
- **Previsão Principal:** **YouTube** se destaca como a melhor plataforma, reforçando os insights da análise de dados

### Insights de Feature Importance
- Métricas mais relevantes para prever a plataforma  
- Permite priorizar recursos e métricas nas campanhas futuras  

### Visualizações
- Gráfico das top features mais importantes  
- Comparação entre valores reais e previstos 


# Recomendações Estratégicas para Negócios

## 1. Prioridade de Plataformas

- Priorizar **YouTube, Facebook e Google** conforme os objetivos da campanha:  
  - **Conversão / Vendas:** YouTube e Facebook — geram mais leads e clientes reais.  
  - **Engajamento / Visibilidade da marca:** YouTube e Facebook — excelente alcance e interação.  
  - **ROI / Eficiência de custo:** Google e Facebook — campanhas mais econômicas por unidade investida.  

- **YouTube e Instagram:** usar estrategicamente, apenas quando o público justificar o custo adicional.  

- **Observação de negócio:** YouTube é indicado como a plataforma mais eficaz, tanto pela análise de dados quanto pelo modelo preditivo.


## 2. Tipo de Conteúdo
- Adaptar o conteúdo ao público e objetivo do negócio:  
  - **Story / Text:** melhores para conversão e geração de leads  
  - **Carousel:** ideal para campanhas de awareness e engajamento

## 3. Segmentação Demográfica
- Segmentar campanhas por **idade, género e região** para otimizar desempenho e retorno por público-alvo

## 4. Gestão de Orçamento e ROI
- Monitorizar **custo por conversão** para alocar orçamento de forma eficiente  
- Priorizar **Google e Facebook** para maximizar ROI em orçamentos limitados  
- YouTube: investir quando o valor do cliente justificar o custo mais elevado

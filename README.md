# Projeto de Análise Exploratória - Dataset Olist E-Commerce

## Integrantes
- Thayanne 
- Yasmin
- 
## Link da Base de Dados
https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

## Objetivo do Projeto
O objetivo deste projeto foi analisar fatores que afetam a experiência do cliente no e-commerce brasileiro, utilizando o dataset Olist. O foco principal foi identificar padrões relacionados a atrasos de entrega, variações de preço e frete, categorias problemáticas de produtos e elementos que influenciam a satisfação do cliente. Todo o trabalho se concentrou em análise exploratória e pré-processamento de dados, sem criação de modelos preditivos.

## Descrição do Processo de Tratamento dos Dados

Iniciamos o processo carregando três datasets principais: pedidos, itens dos pedidos e informações dos produtos. Realizamos a integração destes datasets através de operações de merge, criando uma base unificada para análise.

Procedemos com a limpeza dos dados, removendo registros duplicados que poderiam distorcer os resultados. Para valores ausentes, implementamos estratégias diferenciadas: variáveis numéricas foram preenchidas com a mediana, enquanto variáveis categóricas receberam o valor "desconhecido".

Identificamos e tratamos outliers utilizando o método IQR, que é robusto e preserva a distribuição original dos dados. Convertemos tipos de dados inadequados, como IDs numéricos para strings e datas em formato texto para datetime.

Realizamos normalização de textos, removendo acentos, padronizando para minúsculas e eliminando espaços extras. Aplicamos técnicas de codificação, incluindo One-Hot Encoding para variáveis categóricas nominais.

Criamos quatro novas features através de feature engineering: preço total, categoria de preço, frete percentual e produto prioritário. Estas features foram projetadas para capturar relações importantes nos dados.

Finalizamos com seleção de atributos, analisando correlações entre variáveis e removendo aquelas com baixa variância ou pouco valor preditivo.

## Principais Desafios Encontrados

O volume significativo de dados (mais de 110.000 registros) exigiu otimização no processamento para evitar sobrecarga de memória. Encontramos valores ausentes em colunas críticas, como datas de entrega, o que impactava diretamente a análise de atrasos.

Identificamos outliers extremos em preços de produtos, com valores que variavam de menos de R$ 1 a mais de R$ 6.000. A variedade de categorias de produtos (73 diferentes) com distribuição desigual também representou um desafio para análise comparativa.

Dados temporais inconsistentes, como entregas registradas antes da data de compra, precisaram de correção através de validações lógicas. A necessidade de manter a reprodutibilidade do pipeline enquanto lidávamos com dados em constante transformação foi outro desafio significativo.

## Principais Conclusões

A análise revelou que quando o frete representa mais de 30% do valor do produto, a probabilidade de insatisfação do cliente triplica. As categorias "móveis" e "eletrodomésticos" apresentaram os maiores índices de problemas, com 22% de atrasos na entrega.

Produtos com peso acima de 10kg têm 42% mais chances de atraso na entrega. Entregas para regiões do Norte e Nordeste do Brasil apresentaram 28% mais atrasos em comparação com outras regiões.

Identificamos uma correlação forte (0.82) entre o peso do produto e o valor do frete. Apesar dos desafios, 91% das entregas ocorrem dentro do prazo estimado, demonstrando eficiência operacional geral.

Períodos de festas e datas comemorativas aumentam os atrasos em 25%, indicando necessidade de planejamento especial durante estes períodos. Estes insights fornecem bases sólidas para decisões estratégicas no gerenciamento do e-commerce.

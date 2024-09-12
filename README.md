# Ecommerce-Data-Analytics

Documentação do Código: Análise e Visualização de Dados de Vendas

-1. Visão Geral
Este código foi desenvolvido para realizar a análise e visualização de dados de vendas de uma loja de e-commerce. O código processa um arquivo de vendas em formato Excel, realiza a normalização dos dados, atualiza tabelas de dimensões e de fato, gera visualizações de dados e organiza os arquivos em um DataLake estruturado. O objetivo final é fornecer ao microempreendedor uma visão clara dos dados de vendas para otimizar suas estratégias de marketing e gestão de estoque.

-2. Fluxo do Código
O código segue as seguintes etapas:
2.1 Leitura do Arquivo de Dados
•	Descrição: O código começa verificando o diretório de entrada (/content/drive/MyDrive/DataLake/Entrada/) para identificar o arquivo de vendas que segue o padrão Dataset_xxxxxx.xlsx, onde xxxxxx representa o mês e o ano. O arquivo é então carregado em um DataFrame do pandas.
•	Extração do Mês e Ano: Através de expressões regulares (regex), o código extrai o mês e ano do nome do arquivo para utilizar nas etapas seguintes.
2.2 Atualização das Tabelas de Dimensão
•	Descrição: O código cria ou atualiza três tabelas de dimensão:
o	Dimensão Produto: Contém os produtos únicos vendidos.
o	Dimensão Cliente: Contém os clientes únicos.
o	Dimensão Retenção: Contém os tipos de retenção dos clientes (como canais de aquisição).
•	Processo: Novos registros são adicionados às tabelas de dimensão, evitando duplicações. As tabelas são salvas como arquivos CSV no diretório DatalakeHouse/Banco de Dados.
2.3 Atualização da Tabela Fato
•	Descrição: A tabela fato é criada ou atualizada para armazenar as transações de vendas, unindo as tabelas de dimensão com os dados originais.
•	Processo: Novas transações são verificadas para garantir que dados duplicados não sejam adicionados. A tabela fato final contém colunas como produto_id, cliente_id, retencao_id, Qtd, Custo, Venda, Lucro, Mês, e Data. Ela é salva como um arquivo CSV no diretório DatalakeHouse/Banco de Dados.
2.4 Criação das Visualizações
•	Descrição: O código gera quatro visualizações principais que ajudam a entender os dados de vendas:
o	Distribuição de Vendas por Produto: Um gráfico de barras que mostra a quantidade de vendas para cada produto.
o	Receita Gerada por Produto: Um gráfico de barras que mostra a receita total gerada por cada produto.
o	Distribuição de Clientes por Retenção: Um gráfico de barras que mostra a distribuição dos clientes de acordo com os canais de retenção.
o	Total de Vendas por Mês: Um gráfico de linha que mostra a evolução das vendas ao longo dos meses.
•	Processo: As visualizações são salvas como arquivos PNG no diretório DatalakeHouse/Visualizações.
2.5 Organização dos Arquivos
•	Descrição: Após o processamento, o arquivo de vendas original é movido para o diretório Processados para indicar que já foi processado.
•	Processo: O código verifica se o diretório Processados existe, e o cria se necessário, antes de mover o arquivo.

-3. Requisitos
•	Bibliotecas Python Necessárias:
o	pandas
o	matplotlib
o	seaborn
o	os
o	re

-4. Execução do Código
Para executar o código:
1.	Certifique-se de que o arquivo de vendas esteja no diretório /content/drive/MyDrive/DataLake/Entrada/ com o nome no formato Dataset_xxxxxx.xlsx.
2.	Execute o código em um ambiente como Google Colab.
3.	Verifique o diretório DatalakeHouse para encontrar os arquivos CSV gerados e as visualizações.
4.	O arquivo de vendas original será movido para o diretório Processados.

-5. Personalizações Possíveis
•	Adaptação para Novos Dados: O código pode ser adaptado para processar outros tipos de dados, ajustando as tabelas de dimensões e as visualizações conforme necessário.
•	Integração com Outros Sistemas: O código pode ser integrado com sistemas de automação ou dashboards para atualização automática dos dados e visualizações.
6. Conclusão
Este código fornece uma solução completa para o processamento, análise, e visualização de dados de vendas, permitindo ao microempreendedor tomar decisões informadas com base nos insights gerados.

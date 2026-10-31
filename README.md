Porsche Sales Intelligence — Dashboard Mercado EUA 

Dashboard interativo desenvolvido para a análise estratégica das vendas de veículos da Porsche no mercado norte-americano. A ferramenta permite explorar o volume de vendas, faturamento total, modelos líderes, distribuição geográfica e modalidades de pagamento com atualização dinâmica e em tempo real.  

1. Perguntas de Negócio Escolhidas e Justificativas 

Para proporcionar uma visão executiva completa e orientada a tomada de decisão no setor automotivo premium, foram definidas as seguintes perguntas de negócio: 

Qual é o volume total de unidades vendidas e o faturamento bruto no mercado americano? 

Por quê: Avalia o desempenho financeiro geral e o tamanho da operação no período. 

Quais são os 10 modelos Porsche mais vendidos e qual é a participação de mercado por modelo? 

Por quê: Identifica o mix de produtos mais popular (como 911, Macan, Taycan, Cayenne) para direcionar estratégias de estoque e marketing. 

Como o volume de vendas se distribui ao longo dos anos (2020 a 2026)? 

Por quê: Permite visualizar tendências temporais, sazonalidade e anos de pico nas vendas. 

Quais estados norte-americanos concentram o maior volume de vendas de veículos? 

Por quê: Auxilia na identificação dos mercados regionais mais lucrativos (ex: Califórnia, Flórida, Texas) para planejamento de rede de concessionárias. 

Quais são as principais formas de pagamento utilizadas pelos clientes Porsche? 

Por quê: Entender a proporção entre transferências bancárias, financiamentos, leasing e cartões para otimizar serviços financeiros. 

2. Prompts Utilizados e Evolução das Iterações 

O desenvolvimento do dashboard foi realizado de forma iterativa por meio de engenharia de prompts. A evolução ocorreu nas seguintes etapas: 

Prompt 01 (Inicial): 

"Faça um site de acordo com o .md e use os dados da tabela." 

Resultado: Geração inicial do dashboard HTML/Tailwind/Chart.js estruturado com base nas especificações do data_schema_documentation.md.  

Prompt 02 (Ajustes de UX e Tradução): 

"Faça gráficos e filtros menores, não use as expressões da tabela como palavras com underline, traduza para ficar mais clean, use também os métodos de pagamento que tem na tabela." 

Resultado: Limpeza dos nomes técnicos de banco de dados (car_model $\rightarrow$ Modelo do Veículo), tradução e mapeamento exato dos métodos de pagamento para o português e compactação visual dos controles. 

Prompt 03 (Reformulação dos Gráficos e Layout): 

"Troque o modelo do gráfico em pizza por um modelo de barras horizontais e o modelo de gráfico dos anos por um modelo em pizza, deixe os gráficos menores para que possam ser vistos juntos, coloque as informações abaixo da aba de filtros em espaços menores e um do lado do outro." 

Resultado: Reorganização em grid do dashboard para visualização simultânea dos gráficos sem necessidade de rolar a página. 

Prompt 04 (Ajuste de Escopo e Hierarquia Visual): 

"Nos gráficos, faça o modelo de carros aparecer apenas os 10 mais altos do gráfico em barra HORIZONTAIS, ao lado dele você põe o gráfico de pizza, abaixo você põe o gráfico dos estados, informações na mesma parte do valor total devem ser menores para caber uma do lado da outra, e tire a parte de dados higienizados lá do topo." 

Resultado: Filtragem para os Top 10 modelos, remoção de selos técnicos no cabeçalho e ajuste na distribuição espacial em 2 linhas de gráficos. 

Prompt 05 (Estilo Tipográfico Jornalístico/Editorial): 

"Agora atualize as fontes do site para uma mais jornalística e aumente a fonte dos dados do gráfico de pizza." 

Resultado: Aplicação das fontes Playfair Display (títulos) e Lora (corpo/dados) para conferir um tom de relatório jornalístico e executivo premium. 

Prompt 06 (Aproveitamento de Tela e Legibilidade): 

"Agora deixe maior todas as informações do site, aproveite o espaço do navegador para deixar tudo legível." 

Resultado: Expansão para visualização em tela cheia (w-full), aumento no tamanho das fontes dos cartões KPI, eixos dos gráficos e linhas da tabela detalhada. 

3. Tratamento e Sanitização da Base de Dados 

A base bruta (Tabela arrumada .xlsx) apresentava variações de formatação e valores inconsistentes. Os seguintes tratamentos foram efetuados antes da integração final no código:  

Higienização de Preços (sale_price): Remoção de caracteres de moedas e sufixos ($79,500.00, 235000 USD, USD 112.750, $121k) e conversão para valores numéricos decimais padronizados (DECIMAL(12,2)).  

Padronização de Anos (year): Correção de dados de texto por extenso (ex: twenty twenty four $\rightarrow$ 2024).  

Tratamento de Datas (sale_date): Formatação de datas mistas para o padrão ISO (YYYY-MM-DD) e identificação clara de registros sem data válida como "INVALID" (exibidos na interface como "Não Informada").  

Padronização Geográfica e de Veículos: Correção de capitalização e siglas de estados (ex: boston $\rightarrow$ Boston, tx $\rightarrow$ TX, colorado $\rightarrow$ CO).  

Mapeamento de Formas de Pagamento: Mapeamento de termos diversos (wire transfer, Credit card, Financing plan, CASH, bank-transfer) para categorias padronizadas e exibição amigável em português (ex: Transferência Bancária, Cartão de Crédito, Leasing, Criptomoeda).  

4. Ferramentas de IA Utilizadas 

Gemini (com Web Code Canvas): Utilizado para a criação, prototipação, refatoração de código HTML/JS/Tailwind CSS e ajuste interativo do layout e tipografia em tempo real. 

Execução de Código em Python (Data Science Interpreter): Utilizado para leitura, sanitização, análise estatística e extração do payload JSON a partir da planilha Tabela arrumada .xlsx. 

5. Endereço da Dashboard Publicada 

 

💰 Dashboard de Vendas, Custo, Margem de Lucro e KPI — Power BI
Dashboard financeiro-operacional com foco em rentabilidade, custo logístico e comportamento da margem de lucro ao longo do tempo — permitindo identificar quais mercados, categorias e modos de envio impactam mais o resultado do negócio.

🎯 Problema de negócio
Empresas com operações globais frequentemente monitoram volume de vendas sem correlacionar com custo de envio e margem de lucro por mercado. Este dashboard integra essas três dimensões — valor de venda, custo logístico e margem — para responder perguntas práticas: onde o custo de envio corrói mais a margem? Qual modo de envio concentra mais valor? A margem tem se mantido estável ou há tendência de queda ao longo do tempo?

🔍 Principais insights

Margem de lucro média de 89,08 com ticket médio de R$ 246,49 e custo médio de envio de R$ 26,38 — o custo logístico representa cerca de 10,7% do valor médio de venda, uma proporção relevante para análise de precificação.
APAC e US lideram o custo médio de envio (R$ 29,1 e R$ 28,9 respectivamente), enquanto EMEA e Canadá têm os menores custos (R$ 17,5 e R$ 17,8) — diferença de quase 40% entre os extremos, o que justifica estratégias logísticas diferenciadas por mercado.
Classe Padrão domina o valor total de vendas com R$ 8 Mi, muito acima dos demais modos de envio — o que indica que a maior parte da receita passa pelo modal mais barato, potencialmente favorável à margem.
Tecnologia lidera a média de lucro por categoria com R$ 417,86 (46,55% do total), seguida de Móveis com R$ 371,66 (41,4%) — Material de Escritório, apesar de provavelmente ter maior volume de pedidos, tem a menor média de lucro por categoria.
Margem de lucro oscila entre 88 e 89 ao longo de 2011–2015, sem tendência clara de crescimento ou queda — estabilidade que pode indicar controle operacional consistente, mas também ausência de ganhos de escala.


📄 Estrutura do dashboard
O relatório é composto por uma única página com os seguintes visuais:
VisualDescriçãoKPI — Média de Valor de VendaTicket médio geral das transaçõesKPI — Média de Margem de LucroMargem média no período selecionadoKPI — Média de Custo de EnvioCusto logístico médio por transaçãoMédia de Custo de Envio por MercadoBarras horizontais comparando 7 mercados globaisTotal do Valor de Venda por Modo de EnvioGráfico de cascata (waterfall) com contribuição de cada modalMargem de Lucro ao Longo do TempoSérie temporal de 2011 a 2015 com linha de referência na médiaMédia de Lucro por CategoriaGráfico de rosca com participação de Tecnologia, Móveis e Material de Escritório
Filtro disponível: Ano e Mês (seletor com opção "Todos").

🛠️ Stack técnica
Ferramenta: Power BI Desktop
Transformação de dados (Power Query): alteração de tipos de dado, promoção de cabeçalhos e ajuste da fonte de dados
Visualizações: gráfico de cascata (waterfall) configurado manualmente, série temporal com linha de referência, gráfico de rosca, barras horizontais e cartões KPI com formatação personalizada
Medidas DAX criadas:
As duas métricas centrais do dashboard foram calculadas via colunas DAX criadas diretamente na tabela de vendas:
daxLucro = Vendas[Valor Venda] - Vendas[Custo Envio]
Calcula o lucro bruto por transação, subtraindo o custo logístico do valor de venda.
daxMargem lucro = ROUND( DIVIDE(Vendas[Lucro], Vendas[Valor Venda]) * 100, 2)
Expressa a margem como percentual do valor de venda, arredondada a duas casas decimais. O uso de DIVIDE garante tratamento seguro de divisões por zero.

📊 Fonte dos dados
Dataset de vendas globais com cobertura de 2011 a 2015, originalmente utilizado em curso de formação em dados. O dashboard, os visuais, a formatação e a estrutura analítica foram desenvolvidos de forma independente — incluindo a escolha e configuração dos gráficos, paleta, layout e cruzamentos exibidos.

🔗 Acesse o relatório
Acesse o dashboard

📌 Limitações e próximos passos

Os KPIs exibem médias globais — sem segmentação por mercado ou categoria, um mercado com alto custo de envio e baixa margem pode estar sendo mascarado pela média geral. Próximo passo: adicionar cartões dinâmicos que respondam aos filtros de mercado.
O gráfico de cascata mostra valor absoluto por modo de envio, mas não cruza com margem — seria relevante saber se o modal mais barato (Classe Padrão) também é o mais rentável ou se há trade-off entre prazo e margem.
A série temporal de margem tem granularidade mensal visível no filtro, mas o gráfico exibe por ano — detalhar para visão mensal pode revelar sazonalidade que a visão anual suaviza.

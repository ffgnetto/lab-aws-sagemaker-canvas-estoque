Inicialmente buscando uma experimentação mais pessoal ou fora da caixa, construí um dataset baseado no preço histórico do bitcoin (Abertura, Fechamento, Alta e Baixa, Volume e Capitazação de Mercado).
Após coletar todos os dados do CoinMarketCap.com, organizei na unha todo o template do CSV usando Excel e Notepad, pois o formato direto do CSV gerado pelo CoinMarketCap.com não era bem reconhecido pelo AWS Canvas e nem o gerado pelo Excel, isso me demandou muito tempo e tentativa de várias abordagens, conseguir com exito (está disponível na pasta dataset).

Na hora de treinar o modelo após vários minutos, me deparo com esse erro:

"Unable to build the model
Your model build failed because of an issue with the Canvas server. Failure reason: <Service Internal Error>.Contact your administrator and share the details below to resolve the issue.
If you're an administrator or an individual user, contact AWS support and provide the following code: <d28deb64-5bfa-4166-add3-3758b7caa130> to resolve the issue."

Penso ser algum problema de parâmetro no dataset ou configuração do modelo para predição, altero parâmetros, tento novamente, erro, altero, tento novamente... Após várias tentativas frustradas, decido fazer com os datasets de exemplo.

1. Selecionar Dataset

Usei: dataset-1000-com-preco-promocional-e-renovacao-estoque.csv

3. Construir e Treinar

Fiz o Upload do dataset, configurei o modelo da seguinte forma:
Coluna Alvo: QUANTIDADE_ESTOQUE
Coluna Identificadora: ID_PRODUTO
Coluna de Tempo: DATA_EVENTO
Usar horário de feriado: Brazil
Número de Dia para Predição: 7

5. Analisar

Avg. wQL: 0.226

MAPE: 1.495

WAPE: 0.326

RMSE: 28.478

MASE: 1.284


Baseado no meu entendimento que adquiri com o material complementar sobre as métricas, é possível dizer a maioria foi precisas, pois estão em um nível bem próximo a 0, infelizmente não consegui interpretar a porcentagem de erro do RMSE, se for considerar -28,478% de 100%, como é uma métrica relacionada a média dos valores reais relacionada aos previstos, dá pra dizer que tem uma discrepância.

Alguns itens demonstra nos primeiros 5 dias o P50 bem próximo ao P10, outros a partir do 4ª com todas as métricas bem próximas.


7. Prever
Podemos concluir que podemos se basear no P50 e quando nos dias que ele se aproximar do P90, se basear no P90, para não faltar itens, em uma estratégia de "não perder vendas", sabemos estoque é alocação de recursos e o que gera lucro é sua liquidez, mesmo que sobre poucas unidades, será avaliada novamente na próxima predição para reposiçã.

Tendo como ideia que não podemos ser preciso 100% com o estoque, mas mitigar a alocação de investimento em excesso de produtos que não terão tanta demanda.

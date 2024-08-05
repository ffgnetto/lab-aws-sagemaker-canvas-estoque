Inicialmente buscando uma experimentação mais pessoal ou fora da caixa, construí um dataset baseado no preço histórico do bitcoin (Abertura, Fechamento, Alta e Baixa, Volume e Capitazação de Mercado).
Após coletar todos os dados do CoinMarketCap.com, organizei na unha todo o template do CSV usando Excel e Notepad, pois o formato direto do CSV gerado pelo CoinMarketCap.com não era bem reconhecido pelo AWS Canvas e nem o gerado pelo Excel, isso me demandou muito tempo e tentativa de várias abordagens, conseguir com exito (está disponível na pasta dataset).

Na hora de treinar o modelo após vários minutos, me deparo com esse erro:

"Unable to build the model
Your model build failed because of an issue with the Canvas server. Failure reason: <Service Internal Error>.Contact your administrator and share the details below to resolve the issue.
If you're an administrator or an individual user, contact AWS support and provide the following code: <d28deb64-5bfa-4166-add3-3758b7caa130> to resolve the issue."

Penso ser algum problema de parâmetro no dataset ou configuração do modelo para predição, altero parâmetros, tento novamente, erro, altero, tento novamente... Após várias tentativas frustradas, decido fazer com os datasets recomendados.

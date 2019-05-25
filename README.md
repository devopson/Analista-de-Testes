PROVA ANALISTA DE TESTES

Acesse o link https://www.lingscars.com/ e liste pelo menos dois bugs identificados.

Obs.: os testes foram realizados sobre os browsers Firefox e Chrome

### BUG 1
- retorna link quebrado https://www.lingscars.com/feature/fruitmachine.php?id=532 ao clicar na imagem da bomba de gasolina (carulike_white.png) ou no texto “CAR-U-LIKE-ATOR”.
- a página exibe apenas a mensagem “Fatal error: require(): Failed opening required '../header_min.php' (include_path='.:/usr/share/php') in /srv/www/lingscars.com/public/feature/fruitmachine.php on line 29”  

### BUG 2
- não retorna crítica ao clicar no botão “Update Me!” do form de ID=autoupdate caso não preencha quaisquer dos campos “Name”, “Email” e “Confirm Email” ou os preencha incorretamente.  

### BUG 3
- navegar pelo menu lateral até a opção “Quote” e clicar no banner “Quote Tutorial starring Wong!” aparentemente nada ocorre. Porém, ao tentar clicar nas demais opções do menu (Customers, About Ling, Fun stuff, Free stuff e Live staff) permanece na mesma página pois carregou sobreposta na parte mais abaixo um div id=”help_video”

------------------------------------------------

Selecione dois bugs identificados e elabore um texto para o desenvolvedor reproduzir o bug e corrigi-lo.  

### BUG 1 (passos para reprodução)  
- clicar em qualquer opção de link disponível na lateral esquerda abaixo do label “CARS A-Z” para exibir informações sobre modelos ofertados  
- rolar a tela para baixo até localizar imagem da bomba de gasolina e texto “CAR-U-LIKE-ATOR”  
- clicar na imagem da bomba de gasolina (carulike_white.png) ou no texto “CAR-U-LIKE-ATOR”.  

### BUG 2 (passos para reprodução)  
- clicar em qualquer opção de link disponível na lateral esquerda abaixo do label “CARS A-Z” para exibir informações sobre modelos ofertados  
- clicar em qualquer botão “more info” da order price  
- rolar a página para baixo, localizar e clicar no link <Returning your car>  
- clicar no botão “Update Me! sem ter preenchido quaisquer dos campos do form “AUTO-UPDATES”
    
### BUG 3 (passos para reprodução)
- clicar na opção “Cars” do Menu lateral esquerdo
- clicar na opção “Quote”
- clicar no banner “Quote Tutorial starring Wong!”
- rolar a página para baixo para conseguir visualizar o vídeo tutorial sobre o formulário de cotação  

-------------------------------------------------  

Proponha 4 melhorias para o site e detalhe-as (se julgar necessário, poderá adicionar imagens ou sites de referência).

1. Melhorias na heurística de consistência e padronização entre telas, cores e fontes além de eliminar animações e demais movimentos realizados por meio de gifs e banners animados. 
Exemplo: http://www.zavati.com.br/index.php

2. Melhorias na estética como medida para alcançar um design minimalista revisando e reduzindo a grande quantidade de informações desnecessárias. Quando necessário detalhar um pouco mais alguma informação dispor isso, por exemplo, de forma secundária através de sub menus e retornos de filtros. 
Exemplo: http://www.socarrao.com.br/curitiba-regiao

3. Substituir a extensa lista de links de modelos de carros na lateral esquerda por um menu lateral ou opções de filtros de tal modo que o mesmo fique mais responsivo exibindo os modelos de cada marca ao se clicar no logo ou nome desta e assim cascatear as opções em níveis e subníveis. Além de reduzir a poluição visual e volume de informação exposta antecipadamente evita que o usuário tenha que rolar tantas vezes a página para chegar ao final.
Exemplos: 
https://www.webmotors.com.br/carros-usados/estoque?inst=footer:webmotors:comprar::carros-usados-ou-seminovos
http://autoshoplinhaverde.com.br/busca

4. Revisar e corrigir links quebrados o que pode ser feito, por exemplo através de ferramentas online como dead link checker. Isso assegura confiabilidade ao site e reforça uma melhor experiência ao usuário evitando frustrações. Em um teste que realizei retornou pelo menos 12 falhas em 2000 links analisados.

Referências:
https://blog.caelum.com.br/10-heuristicas-de-nielsen-uma-formula-pra-evitar-erros-basicos-de-usabilidade/
https://www.nngroup.com/articles/ten-usability-heuristics/
https://willianjusten.com.br/varrendo-seu-site-atras-de-links-quebrados/

-------------------------------------------------

Elabore o caso de teste para o caso de uso abaixo:

Caso de uso “Validar Usuário”.
Nome: Validar Usuário

Cenário Principal
    O caso de uso inicia-se quando o sistema apresenta uma tela que pede ao cliente o seu cartão eletrônico.
    O cliente introduz o seu cartão magnético e, através de um pequeno teclado, a sua senha.
    Note-se que o cliente pode limpar a introdução da sua senha inúmeras vezes e re-introduzir um novo número antes de pressionar o botão “Entrar”.

    O cliente ativa o botão “Entrar” para confirmar.
    O sistema lê a senha e a respectiva identificação do cartão, e verifica se é válido.
    Se a senha for válida o sistema aceita a entrada e o caso de uso termina.

Fluxo Alternativo 01: (Cliente cancela operação)
    O cliente pode cancelar a transação em qualquer momento ativando o botão “Cancelar”, implicando a re-inicialização do caso de uso.
    Não é realizada qualquer alteração à conta do cliente.

Fluxo Alternativo 02: (Senha inválida)
    Se o cliente introduz uma senha inválida o cartão MB é ejetado e o caso de uso reinicializado.
    Se tal ocorrer 3 vezes consecutivas, o sistema aciona medidas de segurança e “recolhe” o cartão e cancela a transação; não permitindo qualquer interação nos 2 minutos seguintes.

#### TC1 - cliente utiliza cartão eletrônico válido e senha correta
##### Pré-requisito: sistema exibe tela solicitando cartão eletrônico

| STEP | AÇÃO                                       | RESULTADO ESPERADO                                    |
|------|--------------------------------------------|-------------------------------------------------------|
| 1    | introduzir cartão eletrônico com ID VÁLIDO | cartão recebido na leitora                            |
| 2    | digitar senha VÁLIDA                       | senha com máscara oculta exibida na tela. Ex.: ****** |
| 3    | ativar botão “Entrar”                      | sistema valida o ID do cartão e senha E libera acesso |

#### TC2 - cliente corrige senha informada
##### Pré-requisito: sistema exibe tela solicitando cartão eletrônico

| STEP | AÇÃO                         | RESULTADO ESPERADO                        |
|------|------------------------------|-------------------------------------------|
| 1    | introduzir cartão eletrônico | cartão recebido na leitora                |
| 2    | digitar senha INVÁLIDA       | senha com máscara oculta exibida na tela. |
| 3    | ativar botão “Limpar”        | sistema limpa campo “senha”               |

#### TC3 - cliente cancela operação antes de informar senha
##### Pré-requisito: sistema exibe tela solicitando cartão eletrônico

| STEP 	| AÇÃO                         	| RESULTADO ESPERADO                                                     	|
|------	|------------------------------	|------------------------------------------------------------------------	|
| 1    	| introduzir cartão eletrônico 	| cartão recebido na leitora                                             	|
| 2    	| ativar botão “Cancelar”      	| sistema ejeta cartão da leitora E exibe mensagem “Operação cancelada.” 	|

#### TC4 - cliente cancela operação após informar senha
##### Pré-requisito: sistema exibe tela solicitando cartão eletrônico

| STEP 	| AÇÃO                         	| RESULTADO ESPERADO                                                     	|
|------	|------------------------------	|------------------------------------------------------------------------	|
| 1    	| introduzir cartão eletrônico 	| cartão recebido na leitora                                             	|
| 2    	| digitar senha                	| senha com máscara oculta exibida na tela.Ex.: ******                   	|
| 3    	| ativar botão “Cancelar”      	| sistema ejeta cartão da leitora E exibe mensagem “Operação cancelada.” 	|

#### TC5 - cliente informa senha inválida até três vezes
##### Pré-requisito: sistema exibe tela solicitando cartão eletrônico
                                                                                                   
| STEP | AÇÃO                                       | RESULTADO ESPERADO                                                               |
|------|--------------------------------------------|----------------------------------------------------------------------------------|
| 1    | introduzir cartão eletrônico com ID VÁLIDO | cartão recebido na leitora                                                |
| 2    | digitar senha INVÁLIDA                     | senha com máscara oculta exibida na tela. Ex.: ******                     |
| 3    | ativar botão “Entrar”                      | sistema valida o ID do cartão (OK!)                                       |
|      |                                            | sistema exibe mensagem “Senha não confere!”                               |
|      |                                            | sistema ejeta cartão                                                      |
|      |                                            | sistema imediatamente exibe tela solicitando cartão                       |
| 4    | introduzir cartão eletrônico com ID VÁLIDO | cartão recebido na leitora                                                |
| 5    | digitar senha INVÁLIDA                     | senha com máscara oculta exibida na tela. Ex.: ******                     |
| 6    | ativar botão “Entrar”                      | sistema valida o ID do cartão (OK!)                                       |
|      |                                            | sistema exibe mensagem “Senha não confere! Caso erre 3ª vez o cartão será retido.”|
|      |                                            | sistema ejeta cartão E cancela a operação                                 |  
|      |                                            | sistema imediatamente exibe tela solicitando cartão                       |
| 7    | introduzir cartão eletrônico com ID VÁLIDO | cartão recebido na leitora                                                |
| 8    | digitar senha INVÁLIDA                     | senha com máscara oculta exibida na tela. Ex.: ******                     |
| 9    | ativar botão “Entrar”                      | sistema valida o ID do cartão (OK!)                                       |  
|      |                                            | sistema exibe mensagem “Senha não confere!”                               |  
|      |                                            | sistema recolhe o cartão E cancela a operação                             |  
|      |                                            | sistema exibe tela solicitando cartão somente após 2 minutos seguintes    |
# Analista-de-Testes

PROVA ANALISTA DE TESTES

Acesse o link https://www.lingscars.com/ e liste pelo menos dois bugs identificados.

Selecione dois bugs identificados e elabore um texto para o desenvolvedor reproduzir o bug e corrigi-lo.

Proponha 4 melhorias para o site e detalhe-as (se julgar necessário, poderá adicionar imagens ou sites de referência).

Elabore o caso de teste para o caso de uso abaixo:

Caso de uso “Validar Usuário”. Nome: Validar Usuário Cenário Principal O caso de uso inicia-se quando o sistema apresenta uma tela que pede ao cliente o seu cartão eletrônico. O cliente introduz o seu cartão magnético e, através de um pequeno teclado, a sua senha. Note-se que o cliente pode limpar a introdução da sua senha inúmeras vezes e re-introduzir um novo número antes de pressionar o botão “Entrar”. O cliente ativa o botão “Entrar” para confirmar. O sistema lê a senha e a respectiva identificação do cartão, e verifica se é válido. Se a senha for válida o sistema aceita a entrada e o caso de uso termina.

Fluxo Alternativo 01: (Cliente cancela operação) O cliente pode cancelar a transação em qualquer momento ativando o botão “Cancelar”, implicando a re-inicialização do caso de uso. Não é realizada qualquer alteração à conta do cliente.

Fluxo Alternativo 02: (Senha inválida) Se o cliente introduz uma senha inválida o cartão MB é ejetado e o caso de uso reinicializado. Se tal ocorrer 3 vezes consecutivas, o sistema aciona medidas de segurança e “recolhe” o cartão e cancela a transação; não permitindo qualquer interação nos 2 minutos seguintes.

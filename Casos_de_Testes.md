# Casos de Teste:

�	Nome da Su�te de Teste 1� n�vel:  Valida��o Usu�rio1��, �Itera��o 1�, �M�dulo 1�.
�	Nome da Su�te de Teste 2� n�vel: Validar Usu�rio.
Nome do Caso de Teste: FA001-Validar Usu�rio.
�	Objetivo do Teste: Este caso de teste tem como objetivo verificar se o sistema consegue validar os dados banc�rios do usu�rio.
 Pr�-condi��es: 
O usu�rio deve conter o cart�o eletr�nico da ag�ncia ao qual est� utilizando o ATM.
�	A��es do passo: 
Passo 1 � A��es do passo: Iniciar Retirada - O cliente insere o cart�o banc�rio no leitor de cart�es do caixa eletr�nico;
Passo 1.1 � A��es do passo: Verificar o Cart�o Banc�rio - O caixa eletr�nico l� o c�digo da conta a partir da tarja magn�tica do cart�o banc�rio e verifica se ele � um cart�o aceit�vel;
Passo 1.2 � A��es do passo: Digitar a Senha - O caixa eletr�nico solicita o c�digo de senha do cliente;
Passo 1.3 � A��es do passo: Caso o cliente tenha inserido a senha incorreta, ele poder� fazer a corre��o quantas vezes desejar, sem a necessidade de ser reiniciado o sistema, n�o tendo pressionado o bot�o �ENTRA�;
Passo 1.4 � A��es do passo: Logo quando o cliente est� certo das informa��es inseridas, � pressionado o bot�o �ENTRA�, para confirma��o e sequenciamento.
Passo 1.5 � A��es do passo: Verificar o c�digo da conta e a senha - O c�digo da conta e a senha s�o verificados para determinar se a conta � v�lida e se a senha digitada est� correta para a conta. Para este fluxo, a conta � v�lida e a senha est� corretamente associada a essa conta.
Passo 2 - Fluxo Alternativo 01� A��es do passo: O cliente pode, a qualquer momento, decidir terminar a transa��o (Cancelar). A transa��o � parada e o cart�o ejetado. Sendo necess�rio realizar todos os passos novamente, se pretender realizar outra opera��o.
Passo 3 - Fluxo Alternativo 02� A��es do passo: Na Etapa 1.5 � Verificar Conta e Senha, o cliente tem tr�s chances de digitar a senha correta, se caso for pressionado o bot�o �ENTRA�. Se for digitada uma senha incorreta, o caixa eletr�nico exibir� a mensagem apropriada, e se houver novas tentativas, esse fluxo retornar� � Etapa1.2 Digitar a Senha. Se na �ltima tentativa o n�mero da senha  digitado estiver incorreto, o cart�o ser� retido, o caixa eletr�nico retornar� ao Estado Pronto, e esse caso de uso ser� encerrado, impossibilitando novas atividades por aproximadamente 2 minutos.   


1	Resultados esperados: 
Passo 1 � Resultados Esperados:
O sistema dever� exibir a interface, onde � pedido ao cliente para que seja inserido o seu cart�o banc�rio.
Ap�s ser inserido, o sistema realiza a valida��o do cart�o se est� condizente com o banco selecionado, logo a sua senha de acesso aos servi�os.
O cliente tem a possibilidade de reeditar a sua senha quantas vezes forem necess�rias, caso algum n�mero tenha sido digitado errado, por�m esta possibilidade somente � v�lida caso o cliente n�o tenha pressionado o bot�o �ENTRA� alguma vez.
O sistema banc�rio, realiza toda a sua valida��o com rela��o aos dados obtidos pelo cliente, cogitando a melhor hip�tese de dados corretos, em seguida � mostrada ao cliente todos os servi�os oferecidos pelo banco que o usu�rio pode utilizar.
Ap�s o t�rmino de todas as transa��es que o cliente desejava, o sistema pede o confirma- mento de encerramento de atividades, logo sendo ejetado o cat�o.
Passo 2 � Resultados Esperados: Se em algum momento o cliente desejar cancelar em meio a alguma transa��o, antes de seu cancelamento, dispor uma mensagem como:
�TEM CERTEZA QUE DEJEJA CANCELAR?� -> Com a op��o de sim ou n�o, pois em alguns momentos o usu�rio n�o desejava cancelar, e por algum motivo, o sistema foi deslogado, lhe obrigando a come�ar novamente.
Se o cliente inserir sim, o sistema automaticamente ser� deslogado, reiniciando o sistema novamente, n�o sendo feita nenhuma altera��o na conta do usu�rio.
Passo 3 � Resultados Esperados: Em valida��es de senhas, o esperado em caso de cliente inserir senhas incorretas, em cada tentativa com erro o cart�o � ejetado da m�quina, obrigando o cliente a recome�ar as etapas de acesso novamente, o limite para estas etapas s�o de aproximadamente 3 tentativas, onde caso o cliente persista na senha incorreta, seu cart�o ser� bloqueado, sendo necess�rio ir diretamente a agencia para o desbloqueio ou ligar para o numero de atendimento onde � feito e desbloqueio do mesmo.

## *Flow* de autenticação no github
    
Quando um usuário deseja se logar na nossa aplicação, ele precisa clicar no botão de Login, ao clicar nele, 
o mesmo será direcionado a um form provido pelo github, em que é necessário colocar seu nome de 
usuário e senha (caso o usuário não esteja logado na sua conta do github) como mostra a imagem abaixo:  
`// imagem`  
Se esse é o primeiro acesso, será feito um pedido de autorização para o acesso de algumas informações:  
`//imagem`  
Uma vez que o usuário aceitou as permissões, conseguimos gerar o token, e passá-lo para o front através de uma url de redirecionamento definida no arquivo `.env`, caso as permissões não sejam aceitas, ele será redirecionado para url de erro, também configurada no `.env`, como veremos a seguir.

Certo, tudo muito lindo, mas como fazemos isso funcionar por debaixo dos panos?

Nós, aqui do panelinha de es, somos pessoas que gostam de abstrair ideias a partir de figuras, sendo assim, para que você entenda como se dá a comunicação entre o cliente o servidor, observe a figura abaixo:


![](https://i.imgur.com/Q0uQ9K2.png)

A partir da figura acima, vemos que o cliente, apenas requisita o login e o back abstrai toda a lógica de negócio da autenticação, e ao final de todos os processos, redirecionará, para a url de sucesso ou erro configurada.

Okay, agora que definimos isso, vamos pular para o código.


## Criando uma aplicação GITHUB OAUTH
*COMING SOON*
## Criando um ENV
*COMING SOON*
## Instalando as dependências
*COMING SOON*
## Linkando o server ao front
*COMING SOON*
## Gerenciando o login
*COMING SOON*

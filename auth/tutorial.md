## *Flow* de autenticação no github
    
Quando um usuário deseja se logar na nossa aplicação, ele precisa clicar no botão de Login, ao clicar nele, 
o mesmo será direcionado a um form provido pelo github, em que é necessário colocar seu nome de 
usuário e senha (caso o usuário não esteja logado na sua conta do github) como mostra a imagem abaixo:  
`// imagem`  
Se esse é o primeiro acesso, será feito um pedido de autorização para o acesso de algumas informações:  
`//imagem`  
Uma vez que o usuário aceitou as permissões, o back conseguirá gerar o token, e passá-lo para o front através de uma url de redirecionamento definida no arquivo `.env`, caso as permissões não sejam aceitas, ele será redirecionado para url de erro, também configurada no `.env`, como veremos a seguir.

Certo, tudo muito lindo, mas como fazemos isso funcionar por debaixo dos panos?

Nós, aqui do panelinha de es, somos devs que gostam de abstrair ideias a partir de figuras, sendo assim, para que você entenda como se dá a comunicação entre o cliente o servidor, observe a figura abaixo:


![](https://i.imgur.com/Q0uQ9K2.png)

A partir da figura acima, vemos que o cliente, apenas requisita o login e o back abstrai toda a lógica de negócio da autenticação, e ao final de todos os processos, redirecionará, para a url de sucesso ou erro configurada.

Okay, agora que definimos isso, vamos pular para o código.


## Criando uma aplicação GITHUB OAUTH
Para criar a aplicação do Github OAuth, acesse o github, e siga o seguintes passos:

1. Navegue até a parte de settings.
2. Clique na seção de Developer Settings.
3. Clique no botão para criar uma nova aplicação OAuth.
4. Preencha corretamente as informações necessárias.

## Configurando o servidor
Após termos criado o github oauth app, precisamos configurar nosso servidor, para testar o que definimos anteriormente.

Para isso, baixamos [o projeto do servidor](https://github.com/panelinhadees/server.git), e para que ele funcione corretamente, é necessário criar um  arquivo chamado `.env`, que nos ajuda a definir as configurações necessárias para execução da aplicação, veja o exemplo abaixo.

Podemos dividir as configurações em quatro tipos:
- **Github OAuth**: Configurações relacionadas a configuração da app auth, que criamos no passo anterior.
- **Server**: Configuração da porta, e da url de acesso ao servidor.
- **Client**: Configuração da porta, e da url de acesso ao cliente(você entenderá a seguir porque isso é necessário).
- **Rotas**: As rotas de redirecionamento para o cliente, em caso de erro ou sucesso.

*.env*
```.env
# Required
GITHUB_OAUTH_CLIENT_ID=your-oauth-app-client-id
GITHUB_OAUTH_CLIENT_SECRET=your-oauth-app-client-secret
GITHUB_OAUTH_CALLBACK_URL=your-oauth-app-callback-url

# Optional - Uncomment if you want to change these values
# SERVER_BASE_URL='http://localhost'
# SERVER_PORT=5000

# CLIENT_BASE_URL='http://localhost'
# CLIENT_PORT=8080

# The auth token will be sent to $CLIENT_BASE_URL:$CLIENT_PORT$CLIENT_AUTH_SUCCESS_PATH/:token
# In case of error a message will be sent to $CLIENT_BASE_URL:$CLIENT_PORT$CLIENT_AUTH_ERROR_PATH

# CLIENT_AUTH_SUCCESS_PATH='/auth'
# CLIENT_AUTH_FAIL_PATH='/error'
```

Agora, podemos instalar as dependências e levantar o nosso servidor.

## Instalando as dependências
*COMING SOON*
## Linkando o server ao front
*COMING SOON*
## Gerenciando o login
*COMING SOON*

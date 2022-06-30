# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password:

_{_ <br/>
_"email": "nome@email.com",_<br/>
_"password": "senha"_ <br/>
_}_

Também poderão ser passados valores adicionais não obrigatórios no corpo do cadastro:

_{_ <br/>
_"email": "nome@email.com",_<br/>
_"password": "senha",_ <br/>
_"firstname": "Nome",_<br/>
_"lastname": "Sobrenome",_<br/>
_"age": Number,_<br/>

_}_

<hr/>

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users", email e senha obrigatórios:

_{_ <br/>
_"email": "nome@email.com",_<br/>
_"password": "senha"_ <br/>
_}_

E a resposta deverá conter um token de acesso JWT com as informações do usuário.

_accessToken: _

<hr/>

### Abilities

POST /abilities <br/>
GET /abilities

Utilizando o método POST será necessário o token de autorização do tipo "Bearer", entretando caso seja utilizado o método GET não será necessário, tornando o GET como visibilidade pública. O método POST recebe como body:

_{_
_"primary": "nome_da_habilidade_primária",_<br/>
_"secondary": "nome_da_habilidade_secundária"_<br/>
_}_

#### Podendo ser implementado com qualquer outra chave.

<hr/>

### Weakness

POST /weakness <br/>
GET /weakness

Bem semelhante à rota "abilities" também é utilizado o método POST sendo necessário o token de autorização do tipo "Bearer", caso seja utilizado o método GET não será necessário o token, tornando o GET como visibilidade pública. O método POST recebe como body:

_{_<br/>
_"primary": "nome_da_fraqueza_primária",_<br/>
_"secondary": "nome_da_fraqueza_secundária"_<br/>
_}_

#### Podendo ser implementado com qualquer outra chave.

<hr/>

# Desafio Postgres

Este arquivo fornece um comando para criar um banco de dados PostgreSQL no ambiente do desenvolvedor de forma transparente. 
O comando atende aos seguintes requisitos:

* Nome do banco de dados: curso_docker
* Usuário de acesso: docker_usr
* Senha do usuário: docker_pwd

## Comando

**docker run -d -it -p 5432:5432 \
  -e POSTGRES_USER=docker_usr \
  -e POSTGRES_PASSWORD=docker_pwd \
  -e POSTGRES_DB=curso_docker \
  postgres:latest**

## Explicação do comando:

docker run: Inicia um container. <br>
-d: Executa o BD em modo background. <br>
-it: Permite a interação com o container através de um terminal.
-p 5432:5432: Exporta a porta 5432 do container para a porta 5432 do host. Isso permite que o cliente PostgreSQL do host se conecte ao banco de dados dentro do container. <br>
-e POSTGRES_USER=docker_usr: Define a variável de ambiente POSTGRES_USER com o valor docker_usr. Essa variável é usada para configurar o nome de usuário do banco de dados. <br>
-e POSTGRES_PASSWORD=docker_pwd: Define a variável de ambiente POSTGRES_PASSWORD com o valor docker_pwd. Essa variável é usada para configurar a senha do banco de dados. <br>
-e POSTGRES_DB=curso_docker: Define a variável de ambiente POSTGRES_DB com o valor curso_docker. Essa variável é usada para configurar o nome do banco de dados. <br>
postgres:latest: A imagem do Docker que contém o PostgreSQL.

Uso do comando:

Abra um terminal.
Navegue até o diretório do seu projeto.
Execute o comando docker run mostrado acima.
O container será iniciado e o banco de dados PostgreSQL estará disponível na porta 5432.
Conectando ao banco de dados:

Para se conectar ao banco de dados, você pode usar um cliente PostgreSQL como o psql.

psql -h localhost -p 5432 -U docker_usr -W curso_docker
Observações:

Este comando cria um banco de dados em memória. Isso significa que os dados serão perdidos quando o container for parado.
Se você precisar de um banco de dados persistente, você pode usar um volume Docker para armazenar os dados.

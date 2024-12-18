Frontend - Laravel para API de Produtos

Tecnologias Usadas
Frontend:
Laravel 10
Blade (Template Engine)
Axios (para requisições HTTP)
Banco de Dados:
MySQL (o mesmo usado pela API backend)
Docker:
Docker para configurar e rodar o ambiente de desenvolvimento
Pré-requisitos
Antes de rodar o projeto, verifique se você tem os seguintes pré-requisitos instalados:

PHP (versão 8.1 ou superior)
Composer (para gerenciar dependências do Laravel)
Node.js (necessário para o frontend Laravel)
MySQL (banco de dados)
Docker (caso queira rodar o ambiente com Docker)
Configuração do Frontend (Laravel)

1. Clone o Repositório Frontend
Clone o repositório do frontend Laravel:

git clone (https://github.com/andersonfae/ramada-laravel)
cd produtos-frontend

2. Instale as Dependências do Laravel
Certifique-se de que o PHP e o Composer estão configurados corretamente. Para instalar as dependências do Laravel, execute o seguinte comando:

composer install

3. Configure o Banco de Dados
Edite o arquivo .env para configurar a conexão com o banco de dados (caso necessário). A configuração do banco de dados é a mesma utilizada pela API backend (MySQL):

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=api_produtos
DB_USERNAME=root
DB_PASSWORD=yourpassword

4. Execute o Servidor Laravel
Com todas as dependências instaladas e o banco de dados configurado, você pode executar o servidor Laravel localmente:

php artisan serve

Isso iniciará o servidor Laravel, que estará acessível em http://127.0.0.1:8000.

Funcionalidades
A interface frontend permite a interação com os produtos da API com as seguintes funcionalidades:

Listagem de Produtos
Exibe todos os produtos em uma tabela com paginação, permitindo ao usuário visualizar os produtos de forma organizada.

Busca e Filtro
Permite buscar produtos por nome e aplicar filtros por categoria e faixa de preço. A busca é realizada diretamente via requisições HTTP para a API.

Cadastro de Produto
Formulário para adicionar novos produtos à base de dados. Ao submeter o formulário, a API é chamada para inserir o novo produto.

Edição de Produto
Formulário para editar produtos existentes. O usuário pode modificar detalhes do produto e submeter as alterações, que serão refletidas na API.

Importação em Massa
Interface para upload de arquivos (JSON ou CSV) contendo produtos. Isso permite a importação em massa de produtos de uma vez, facilitando o processo de inserção de dados.

Exclusão de Produto
Exclusão de produtos com uma confirmação antes da exclusão definitiva. O produto será removido da base de dados ao confirmar a ação.

Mensagens de Feedback
Após cada operação (adição, edição, exclusão ou importação de produtos), mensagens de sucesso ou erro são exibidas na interface, informando ao usuário sobre o status da ação.

Exemplos de mensagens:

"Produto adicionado com sucesso!"
"Erro ao editar produto."
"Produto excluído com sucesso."
Rodando o Ambiente com Docker (Opcional)
Para rodar o ambiente completo com Docker (frontend + backend + MySQL), temos um arquivo docker-compose.yml configurado.

1. Configuração do Docker
No diretório raiz do seu projeto (onde se encontra o arquivo docker-compose.yml), execute:

docker-compose up --build

Este comando vai construir os containers e iniciar os serviços (frontend, backend e banco de dados). O Laravel estará acessível em http://127.0.0.1:8000, enquanto a API backend estará em http://127.0.0.1:8081.

2. Acessando os Containers Docker
Se precisar acessar um container, use o comando abaixo:

docker exec -it nome_do_container bash

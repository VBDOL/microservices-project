# Projeto de Microsserviços com Docker

## Descrição

Este projeto é uma implementação de uma estrutura de microsserviços utilizando Docker, com foco em boas práticas e otimização de recursos. O objetivo é provisionar e conectar um serviço web em PHP a um banco de dados MySQL, simulando uma arquitetura moderna de microsserviços.

O projeto também inclui configurações para o servidor NGINX e automação da criação da tabela de dados no banco, além de ser facilmente escalável.

---

## Estrutura do Projeto

```plaintext
microservices-project/
├── database/
│   └── banco.sql          # Script SQL para criação da tabela no banco
├── web/
│   ├── Dockerfile         # Configuração do contêiner para o serviço web
│   ├── index.php          # Script PHP para interagir com o banco de dados
│   └── nginx.conf         # Configuração do servidor NGINX
├── docker-compose.yml     # Orquestração dos serviços
└── README.md              # Documentação do projeto

````
** Tecnologias Utilizadas
Docker: Para criar e gerenciar contêineres.

PHP: Utilizado como linguagem backend para manipulação dos dados.

NGINX: Servidor web para entregar o serviço PHP.

MySQL: Banco de dados relacional para armazenamento das informações.

Docker Compose: Para orquestrar os contêineres e simplificar a execução.

Pré-requisitos
Antes de começar, certifique-se de ter instalado:

Docker (versão 20.x ou superior)

Docker Compose (versão 1.29 ou superior)

Além disso, conhecimentos básicos em Linux, Docker e AWS são recomendados para melhorias ou implantação em ambientes de produção.

Como Executar o Projeto
Clone o repositório:

bash
git clone https://github.com/SeuUsuario/microservices-project.git
cd microservices-project
Certifique-se de que a porta 4500 (para o serviço web) e 3306 (para o banco de dados MySQL) estão disponíveis no seu ambiente.

Construa e inicie os contêineres:

bash
docker-compose up --build
Acesse o serviço web no navegador:

http://localhost:4500
Estrutura e Funcionamento
Serviço Web
PHP é usado para inserir registros aleatórios na tabela dados no banco de dados.

O NGINX serve como proxy reverso e entrega as páginas do serviço.

Banco de Dados
O MySQL é configurado com credenciais padrão e inicializado automaticamente com o script banco.sql, que cria a tabela necessária.

Orquestração
O Docker Compose gerencia os dois serviços, garantindo que o banco de dados seja inicializado antes do serviço web.

Funcionalidades
Inserção Dinâmica: Registros são criados dinamicamente no banco de dados para cada acesso ao serviço web.

Configuração Personalizada: NGINX configurado para suportar PHP-FPM.

Fácil Implantação: Com apenas um comando, todos os serviços são provisionados.

Melhorias Futuras
Segurança:

Substituir credenciais estáticas por variáveis de ambiente.

Configurar HTTPS no NGINX.

Escalabilidade:

Adicionar um balanceador de carga para lidar com múltiplas réplicas do serviço web.

Monitoramento:

Integrar ferramentas como Prometheus e Grafana para monitorar o desempenho.

Deploy em Nuvem:

Configurar a infraestrutura para execução no AWS ECS, Fargate ou Kubernetes.

Contribuição
Contribuições são bem-vindas! Sinta-se à vontade para criar um fork, abrir issues ou enviar pull requests.

Licença
Este projeto é licenciado sob a MIT License.

Desfrute do projeto! 🚀

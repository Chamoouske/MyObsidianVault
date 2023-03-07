- Logo ou banner
    - Status: Opcional
    - A logo ou banner pode substituir o título do projeto mas não a descrição.
- Título e Descrição
    - Status: Obrigatório
    - Título: Nome curto do projeto
    - Descrição: Uma breve descrição do objetivo do projeto
- Badges
    - Status: Opcional
    - As badges podem ficar no topo antes do título ou abaixo da descrição
    - [shields.io](http://shields.io)
- Tabela de conteúdos
    - Status: Obrigatório
    - Tabela onde a pessoa clica e vai para o tópico específico
- Status do projeto
    - Status: Obrigatório
    - Indica se o projeto está em desenvolvimento ou já foi concluído
- Features
    - Status: Opcional
    - Lista das funcionalidades da aplicação
- Demonstração da aplicação
    - Status: Opcional
- Pré-requisitos e como rodar a aplicação/testes
    - Status: Obrigatório
    - Montar o passo-a-passo para rodar a aplicação
- Tecnologias utilizadas
    - Status: Obrigatório (para projetos de estudos/portfólio)
- Contribuição
    - Status: Opcional
    - Listar os nomes de quem contribuiu com o projeto
- Autor
    - Status: Obrigatório
    - Colocar as redes sociais do autor
- Licença
    - Status: Obrigatório
    - Definição da Licença do projeto
- Exemplo:
    
    ```markdown
    <h1 align="center">Título do projeto</h1>
    
    <div style="text-align:justify;">
    Breve Descrição do projeto
    </div>
    
    <div align="center">
    
    ---
    ![Issues](https://img.shields.io/github/issues/UserGithub/NameRepo)
    ![Forks](https://img.shields.io/github/forks/UserGithub/NameRepo)
    ![Stars](https://img.shields.io/github/stars/UserGithub/NameRepo)
    ![Licence](https://img.shields.io/github/license/UserGithub/NameRepo)
    </div>
    
    - [Features](#features)
    - [Demonstração da aplicação](#demonstração-da-aplicação)
    - [Pré-requisitos](#pré-requisitos)
    - [Rodando a aplicação](#rodando-a-aplicação)
    - [Tecnologias](#tecnologias)
    - [Autor](#autor)
    
    <div align="center">
    
    ![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-%233059c1?style=for-the-badge)
    </div>
    
    ## Features
    ---
    - [x] CRUD Impressoras
    - [x] CRUD Manutenções
    - [ ] Sistema de login
    
    ## Demonstração da aplicação
    ---
    <div style="text-align:justify;">
    
    Tem um exemplo de como a aplicação funciona [aqui](https://control-printers-maintenance.herokuapp.com/), o deploy deste exemplo foi usando a plataforma [Heroku](https://www.heroku.com).
    </div>
    
    ## Pré-requisitos
    ---
    <div style="text-align:justify;">
    
    Por se tratar de uma aplicação em Flask, será necessário ter instalado na máquina que será o servidor, o [Python](https://www.python.org/) antes de tudo, junto com o [Git](https://git-scm.com), ou apenas baixar o repositório zipado [aqui](https://github.com/Chamoouske/PrintersMaintenanceFlask/archive/refs/heads/main.zip) e seguir os passos descritos após o passo para clonar o repositório.
    </div>
    
    ## Rodando a aplicação
    ---
    <div style="text-align:justify;">
    
    Caso seja usado um Banco de Dados já criado, altere o caminho expecificado na linha 8 do arquivo [db_manager.py](/src/controller/db_manager.py), seguindo as instruções do [SQLAlchemy](https://docs.sqlalchemy.org/en/14/core/engines.html). Caso contrário, a aplicação criará um arquivo chamado database.db, que armazenará os dados alimentados na aplicação.
    
    Após esses detalhes, seguiremos com os seguintes passos:
    
    ```bash
    # Clone o repositório
    git clone https://github.com/Chamoouske/PrintersMaintenanceFlask.git
    
    # Acesse a pasta do projeto
    cd PrintersMaintenanceFlask
    
    # Crie um ambiente virtual antes de prosseguir, siga os passos descritos em <https://docs.python.org/pt-br/3/library/venv.html> para criar
    # Instale as depêndencias
    pip install -r requeriments.txt
    
    # Execute a aplicação
    py app.py
    
    # A aplicação irá rodar na porta 5000 - acesse <http://localhost:5000>
    
    </div>
    
    ## Tecnologias
    ---
    Este projeto fez uso das seguintes tecnologias:
    
    - [Python](https://www.python.org/)
    - [Flask](https://flask.palletsprojects.com/en/2.1.x/)
    - [SQLAlchemy](https://www.sqlalchemy.org/)
    - [Gunicorn](https://gunicorn.org/) (Usado apenas para realizar o deply pelo Heroku, pode ser removido do arquivo [requirements.txt](requirements.txt))
    
    ## Autor
    ---
    <a href='https://github.com/Chamoouske' target="_blank">
    <img src="https://github.com/Chamoouske.png" style="width:100px" />
    
    Ajax Lima
    </a>
    
    Feito com ❤️ por Ajax Lima
    
    [![Twitter Badge](https://img.shields.io/badge/-@chamoouske-1ca0f1?style=flat-square&labelColor=1ca0f1&logo=twitter&logoColor=white&link=https://twitter.com/chamoouske)](https://twitter.com/chamoouske)
    [![Linkedin Badge](https://img.shields.io/badge/-Ajax%20Lima-blue?style=flat-square&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/ajaxlima/)](https://www.linkedin.com/in/ajaxlima/)
    [![Gmail Badge](https://img.shields.io/badge/-ajaxlima94@gmail.com-c14438?style=flat-square&logo=Gmail&logoColor=white&link=mailto:ajaxlima94@gmail.com)](mailto:ajaxlima94@gmail.com)
    
    <div align="center">
    
    ![Licence](https://img.shields.io/github/license/Chamoouske/PrintersMaintenanceFlask)
    </div>
    ```
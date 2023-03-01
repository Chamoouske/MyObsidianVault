# Guia init Django

[E[strutura de pastas no Django](https://www.delftstack.com/pt/howto/django/django-project-structure/)](Guia%20init%20Django%20f523e86ba585467fb1cd3303796bb9e2/Estrutura%20de%20pastas%20no%20Django%202c14845a01aa4e039011b21e69b28c13.md)

[Define global template](Guia%20init%20Django%20f523e86ba585467fb1cd3303796bb9e2/Define%20global%20template%209b59d5ed9d054fa2b4b2b0a32ddfc7df.md)

```bash
mkdir myproject && cd myproject && py -m venv venv && pip install django
```

```bash
django-admin startproject nameproject
```

```bash
cd nameproject && py manage.py startapp nameapp
```

Sempre que iniciar um novo app django, precisa adicionar a url dele no arquivo urls.py na pasta com o nome dado no comando django-admin startproject

No arquivo settings.py na pasta criada pelo django-admin startproject, está a parte de alterar o uso do banco de dados. Mais detalhes estão [aqui](https://docs.djangoproject.com/en/4.1/intro/tutorial02/).

- Criar um super usuário:
    
    ```bash
    py manage.py createsuperuser
    ```
# Guia init Django

[Estrutura de pastas no Django](Estrutura%20de%20pastas%20no%20Django.md)

[Define global template](Define%20global%20template.md)

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
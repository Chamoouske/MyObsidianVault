---
tag: ajuda
---

- Lista de comandos para Heroku CLI
    - Login Heroku
        
        ```bash
        heroku login
        ```
        
    - Clone Repo Heroku
        
        ```bash
        heroku git:clone -a nameOfProjectOnHeroku
        ```
        
    - Change Dir
        
        ```bash
        cd nameOfProjectOnHeroku
        ```
        
    - Create Procfile
        
        ```bash
        worker: python main.py
        ```
        
    - Add changes to git repo
        
        ```bash
        git add .
        ```
        
        ```bash
        git commit -m “Message of commit”
        ```
        
    - Create branch in Heroku
        
        ```bash
        heroku git:remote -a nameOfProject
        ```
        
    - Upload changes to Repo on Heroku
        
        ```bash
        git push heroku main
        ```
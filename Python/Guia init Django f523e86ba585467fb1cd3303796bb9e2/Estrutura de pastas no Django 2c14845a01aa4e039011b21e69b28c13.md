# Estrutura de pastas no Django

- Project folder
    
    .gitignore
    
    LICENSE.md or LICENSE.rst
    
    README.md or README.rst
    
    environment
    
    requirements.txt
    
    - Documentation
        
        
    - MyProject
        
        manage.py
        
        - media
        - MyProject
            
            __**init__ .py**
            
            - settings
                
                __**init__.py**
                
                base.py
                
                development.py
                
                production.py
                
                .env
                
            
            urls.py
            
            wsgi.py
            
        - AppOne
            - static
                - AppOne
            - templates
                - AppOne
            
            models.py
            
            urls.py
            
            views.py
            
        - AppTwo
            - static
                - AppTwo
            - templates
                - AppTwo
            
            models.py
            
            urls.py
            
            views.py
            
        - AppThree
            - static
                - AppThree
            - templates
                - AppThree
            
            models.py
            
            urls.py
            
            views.py
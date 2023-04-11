
- Criar ambiente virtual
    
    ```bash
    conda create --name (-n) <ENV_NAME>
    ```
    
- Listar ambientes criados
    
    ```bash
    conda env list
    ```
    
- Mudar ambiente virtual
    
    ```bash
    activate <ENV_NAME>
    ```
    
- Sair do ambiente virtual
    
    ```bash
    deactivate
    ```
    
- Excluir um ambiente virtual
    
    ```bash
    conda env remove --name (-n) <ENV_NAME>
    ```
    
- Clonar um ambiente virtual
    
    ```bash
    conda create -n <NEW_ENV_NAME> --clone <CLONE_ENV_NAME>
    ```
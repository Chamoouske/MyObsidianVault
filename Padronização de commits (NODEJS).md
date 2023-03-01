- Instalação das libs usadas:
    - Usando o Yarn:
        
        ```bash
        yarn add husky @commitlint/config-conventional @commitlint/cli -D
        yarn add commitzen -G
        ```
        
    - Usando o npm:
        
        ```bash
        npm install -d husky @commitlint/config-conventional @commitlint/cli
        npm install -g commitzen
        ```
        
- Inicialização do commitizen
    
    ```bash
    commitizen init cz-conventional-changelog --yarn --dev --exact
    ```
    
- Configuração no arquivo package.json do projeto
    
    ```json
    "scripts": {
        		"commit": "git-cz"
      	},
    	"husky": {
    		"hooks": {
    			"commit-msg": "commitlint -E HUSKY_GIT_PARAMS",
    			"prepare-commit-msg": "exec < /dev/tty && git cz --hook || true"
    		}
    	}
    ```
    
- Criar o arquivo commitlint.config.js na raiz do projeto com o seguinte código:
    
    ```js
    module.exports = {
    	extends: ['@commitlint/config-conventional']
    }
    ```
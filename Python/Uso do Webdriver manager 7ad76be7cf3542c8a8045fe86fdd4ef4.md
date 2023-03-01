# Uso do Webdriver manager

Primeiro precisa instalar o webdriver_manager com o comando:

```bash
pip install webdriver_manager
```

No arquivo de uso do webdriver, usar o código abaixo, para usar o manager e baixar automaticamente o webdriver mais atual

```python
from selenium import webdriver
from webdriver_manager.chrome import ChromeDriverManager
from selenium.webdriver.chrome.service import Service

servico = Service(ChromeDriverManager().install())
navegador = webdriver.Chrome(service=servico)
```
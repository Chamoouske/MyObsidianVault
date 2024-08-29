
- [ ] Singleton
## O que é?
O Singleton é um padrão que impede que mais de uma instância de um objeto seja criada, sendo assim, apenas uma instância daquele objeto pode existir e é retornada quando é executado a instrução para criar uma nova instância.

## Exemplo
```python
class Classe:
	_instance = None
	nome = None
	def __init__(self, nome, *args, **kwargs):
		self.nome = nome

	def __new__(self, *args, **kwargs):
		if(_instance == None)
			_instance = new Classe(*args, **kwargs)

		return _instance

classe1 = Classe("classe 1")
classe2 = Classe("classe 2")

print(classe1.nome) # Saída é: "classe 1"
print(classe2.nome) # Saída é: "classe 1"
```
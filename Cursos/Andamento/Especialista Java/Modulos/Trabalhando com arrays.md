---
tags:
  - cursos/modulos
completed: true

---

```dataviewjs
const { update } = this.app.plugins.plugins['metaedit'].api;

(async function updatePercentTasks() {
	const tasksModulos = dv.current().file.tasks;
	const incompletedTasks = tasksModulos.where(t=>!t.completed).length;
	
	if(incompletedTasks == 0)
		await update('completed', true, dv.current().file.path);
	else if(dv.current().completed) await update('completed', false, dv.current().file.path);
})()
```
---
- [x] [Declarando e inicializando arrays](https://app.algaworks.com/aulas/4459/declarando-e-inicializando-arrays)
- [x] [Acessando e atribuindo elementos de arrays](https://app.algaworks.com/aulas/4460/acessando-e-atribuindo-elementos-de-arrays)
- [x] [Iterando em arrays](https://app.algaworks.com/aulas/4461/iterando-em-arrays)
- [x] [Transformando arrays em representações em string](https://app.algaworks.com/aulas/4462/transformando-arrays-em-representacoes-em-string)
- [x] [Ordenando arrays em ordem natural e reversa](https://app.algaworks.com/aulas/4463/ordenando-arrays-em-ordem-natural-e-reversa)
- [x] [Criando arrays de objetos](https://app.algaworks.com/aulas/4464/criando-arrays-de-objetos)
- [x] [Iterando em arrays de objetos](https://app.algaworks.com/aulas/4465/iterando-em-arrays-de-objetos)
- [x] [Copiando e expandindo arrays](https://app.algaworks.com/aulas/4466/copiando-e-expandindo-arrays)
- [x] [Removendo elementos de arrays](https://app.algaworks.com/aulas/4467/removendo-elementos-de-arrays)
- [x] [Desafio: arrays](https://app.algaworks.com/aulas/4468/desafio-arrays)
- [x] [Um pouco da ArrayList da Collections API](https://app.algaworks.com/aulas/4469/um-pouco-da-arraylist-da-collections-api)
- [x] [Desafio: ArrayList](https://app.algaworks.com/aulas/4470/desafio-arraylist)
- [x] [Diagrama de classes: multiplicidade para arrays](https://app.algaworks.com/aulas/4471/diagrama-de-classes-multiplicidade-para-arrays)
- [x] [Boas práticas: retorne arrays ou coleções vazias no lugar de null](https://app.algaworks.com/aulas/4472/boas-praticas-retorne-arrays-ou-colecoes-vazias-no-lugar-de-null)
- [x] [Criando arrays multidimensionais](https://app.algaworks.com/aulas/4473/criando-arrays-multidimensionais)
- [x] [Iterando em arrays multidimensionais](https://app.algaworks.com/aulas/4474/iterando-em-arrays-multidimensionais)
- [x] [Lendo os parâmetros da linha de comando](https://app.algaworks.com/aulas/4475/lendo-os-parametros-da-linha-de-comando)
- [x] [Criando métodos com argumentos variáveis com Varargs](https://app.algaworks.com/aulas/4476/criando-metodos-com-argumentos-variaveis-com-varargs)
- [x] [Boas práticas: use varargs com cuidado](https://app.algaworks.com/aulas/4477/boas-praticas-use-varargs-com-cuidado)
- [x] [Desafio: varargs](https://app.algaworks.com/aulas/4478/desafio-varargs)
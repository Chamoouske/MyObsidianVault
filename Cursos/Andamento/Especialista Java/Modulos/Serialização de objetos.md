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
1. [x] [Introdução à serialização de objetos1m 34s](https://app.algaworks.com/aulas/4889/introducao-a-serializacao-de-objetos)
2. [x] [Tornando classes serializáveis com a interface Serializable2m 39s](https://app.algaworks.com/aulas/4890/tornando-classes-serializaveis-com-a-interface-serializable)
3. [x] [Serializando objetos com ObjectOutputStream7m 38s](https://app.algaworks.com/aulas/4891/serializando-objetos-com-objectoutputstream)
4. [x] [Desserializando objetos com ObjectInputStream7m 54s](https://app.algaworks.com/aulas/4892/desserializando-objetos-com-objectinputstream)
5. [x] [Ignorando propriedades com transient2m 39s](https://app.algaworks.com/aulas/4893/ignorando-propriedades-com-transient)
6. [x] [Entendendo e gerando serialVersionUID10m 24s](https://app.algaworks.com/aulas/4894/entendendo-e-gerando-serialversionuid)
7. [x] [Boas práticas de serialização e serialVersionUID6m 54s](https://app.algaworks.com/aulas/4895/boas-praticas-de-serializacao-e-serialversionuid)
8. [x] [Desafio: serialização de objetos1m 16s](https://app.algaworks.com/aulas/4896/desafio-serializacao-de-objetos)
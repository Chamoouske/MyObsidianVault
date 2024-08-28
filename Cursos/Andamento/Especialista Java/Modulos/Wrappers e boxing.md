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
1. [x] [Usando classes wrapper10m 50s](https://app.algaworks.com/aulas/4432/usando-classes-wrapper)
2. [x] [Métodos de conversão5m 31s](https://app.algaworks.com/aulas/4433/metodos-de-conversao)
3. [x] [Autoboxing e unboxing4m 14s](https://app.algaworks.com/aulas/4434/autoboxing-e-unboxing)
4. [x] [Comparando wrappers12m 49s](https://app.algaworks.com/aulas/4435/comparando-wrappers)
5. [x] [Desafio: wrappers e boxing](https://app.algaworks.com/aulas/4436/desafio-wrappers-e-boxing)
6. [x] [Boas práticas: prefira tipos primitivos a wrappers18m 47s](https://app.algaworks.com/aulas/4437/boas-praticas-prefira-tipos-primitivos-a-wrappers)
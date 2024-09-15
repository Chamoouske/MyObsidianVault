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
1. [x] [Rigidez do código com herança20m 36s](https://app.algaworks.com/aulas/4559/rigidez-do-codigo-com-heranca)
2. [x] [Boas práticas: prefira composição em vez de herança de classes29m 36s](https://app.algaworks.com/aulas/4560/boas-praticas-prefira-composicao-em-vez-de-heranca-de-classes)
3. [x] [Código frágil: alto acoplamento com herança28m 24s](https://app.algaworks.com/aulas/4561/codigo-fragil-alto-acoplamento-com-heranca)
4. [x] [Boas práticas: reduzindo acoplamento com composição15m 14s](https://app.algaworks.com/aulas/4562/boas-praticas-reduzindo-acoplamento-com-composicao)
5. [x] [Decorator Pattern: consolidando os conhecimentos18m 19s](https://app.algaworks.com/aulas/4563/decorator-pattern-consolidando-os-conhecimentos)
6. [x] [Boas práticas: projete interfaces com cuidado10m 40s](https://app.algaworks.com/aulas/4564/boas-praticas-projete-interfaces-com-cuidado)
7. [x] [Boas práticas: use interfaces apenas para definir tipos8m 19s](https://app.algaworks.com/aulas/4565/boas-praticas-use-interfaces-apenas-para-definir-tipos)
8. [x] [Boas práticas: referencie objetos por suas interfaces10m 37s](https://app.algaworks.com/aulas/4566/boas-praticas-referencie-objetos-por-suas-interfaces)
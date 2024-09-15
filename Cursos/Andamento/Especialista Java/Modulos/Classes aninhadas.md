---
tags:
  - cursos/modulos
completed: false

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
1. [x] [Introdução às classes aninhadas3m 46s](https://app.algaworks.com/aulas/4783/introducao-as-classes-aninhadas)
2. [x] [Classes aninhadas estáticas14m 14s](https://app.algaworks.com/aulas/4784/classes-aninhadas-estaticas)
3. [x] [Modificadores de acesso de classes aninhadas6m 36s](https://app.algaworks.com/aulas/4785/modificadores-de-acesso-de-classes-aninhadas)
4. [x] [Enum como membro estático de uma classe3m 13s](https://app.algaworks.com/aulas/4786/enum-como-membro-estatico-de-uma-classe)
5. [x] [Classes aninhadas não-estáticas14m 49s](https://app.algaworks.com/aulas/4787/classes-aninhadas-nao-estaticas)
6. [x] [Shadowing em classes aninhadas5m 9s](https://app.algaworks.com/aulas/4788/shadowing-em-classes-aninhadas)
7. [x] [Classes locais14m 57s](https://app.algaworks.com/aulas/4789/classes-locais)
8. [x] [Classes anônimas8m 13s](https://app.algaworks.com/aulas/4790/classes-anonimas)
9. [x] [Desafio: classes aninhadas3m 14s](https://app.algaworks.com/aulas/4791/desafio-classes-aninhadas)
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
1. [x] [Upcasting de referências28m 7s](https://app.algaworks.com/aulas/4533/upcasting-de-referencias)
2. [x] [O problema que polimorfismo resolve12m 26s](https://app.algaworks.com/aulas/4534/o-problema-que-polimorfismo-resolve)
3. [x] [Entendendo o polimorfismo18m 7s](https://app.algaworks.com/aulas/4535/entendendo-o-polimorfismo)
4. [x] [Downcasting de referências19m 4s](https://app.algaworks.com/aulas/4536/downcasting-de-referencias)
5. [x] [Operador instanceof9m 41s](https://app.algaworks.com/aulas/4537/operador-instanceof)
6. [x] [Pattern Matching para o operador instanceof6m 27s](https://app.algaworks.com/aulas/4538/pattern-matching-para-o-operador-instanceof)
7. [x] [Evitando o uso de instanceof14m 21s](https://app.algaworks.com/aulas/4539/evitando-o-uso-de-instanceof)
8. [x] [Criando um projeto de faturamento21m 7s](https://app.algaworks.com/aulas/4540/criando-um-projeto-de-faturamento)
9. [x] [Classes abstratas9m 43s](https://app.algaworks.com/aulas/4541/classes-abstratas)
10. [x] [Métodos abstratos8m 14s](https://app.algaworks.com/aulas/4542/metodos-abstratos)
11. [x] [Desafio: polimorfismo e classes abstratas13m 29s](https://app.algaworks.com/aulas/4543/desafio-polimorfismo-e-classes-abstratas)
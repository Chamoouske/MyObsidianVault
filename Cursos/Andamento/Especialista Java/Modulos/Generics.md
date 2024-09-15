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
1. [x] [Introdução aos Generics16m 34s](https://app.algaworks.com/aulas/4664/introducao-aos-generics)
2. [x] [Implementando métodos genéricos17m 47s](https://app.algaworks.com/aulas/4665/implementando-metodos-genericos)
3. [x] [Delimitando tipos genéricos15m 30s](https://app.algaworks.com/aulas/4666/delimitando-tipos-genericos)
4. [x] [Criando classes genéricas17m 25s](https://app.algaworks.com/aulas/4667/criando-classes-genericas)
5. [x] [Criando interfaces genéricas10m 9s](https://app.algaworks.com/aulas/4668/criando-interfaces-genericas)
6. [x] [Usando curingas para tipos desconhecidos16m 9s](https://app.algaworks.com/aulas/4669/usando-curingas-para-tipos-desconhecidos)
7. [x] [Desafio: Generics3m 52s](https://app.algaworks.com/aulas/4670/desafio-generics)

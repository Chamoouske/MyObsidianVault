---
status: To Do
priority: Moderate
until: 
project: Personal

Total: 2
Complete: 0
Incomplete: 2
---
```dataviewjs
const {update} = this.app.plugins.plugins['metaedit'].api;

(async function updatePercentTasks(){
	const tasks = dv.current().file.tasks;
	const completedTasks = tasks.where(t=>t.completed).length;
	const incompletedTasks = tasks.where(t=>!t.completed).length;
	
	if(tasks.length != dv.current().Total)
		await update('Total', tasks.length, dv.current().file.path);
	if(completedTasks != dv.current().Complete)
		await update('Complete', completedTasks, dv.current().file.path);
	if(incompletedTasks != dv.current().Incomplete)
		await update('Incomplete', incompletedTasks, dv.current().file.path);
})()
```
## Description
Criar um Gestor de tarefas com datas, status e coisas relacionadas

## Tasks
- [ ] Criar requisitos funcionais
- [ ] Criar requisitos não funcionais
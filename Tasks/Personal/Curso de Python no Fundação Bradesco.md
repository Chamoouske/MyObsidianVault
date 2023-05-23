---
status: Completed
priority: Moderate
until: 2023-07-12
project: Personal

Total: 4
Complete: 4
Incomplete: 0
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
Curso de desenvolvimento de projetos Python com estrutura de dados

## Tasks
- [x] Ambiente de Desenvolvimento
- [x] Estrutura de dados
- [x] SQL
- [x] Python e SQLite
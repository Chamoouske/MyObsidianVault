---
status: In Progress
priority: Moderate
until: 2023-06-10
project: GTRR

Total: 5
Complete: 5
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
Criar o cofre da Curadoria no Obsidian e GitHub

## Histórico
- Reunião dia 25/05/2023

## Tasks
- [x] Criar o cofre
- [x] Verificar as informações que precisa pros templates
- [x] Criar os templates que serão usados
- [x] Configurar os plugins do obsidian
- [x] Disponibilizar o repositório do cofre
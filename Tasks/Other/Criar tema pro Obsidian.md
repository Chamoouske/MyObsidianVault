---
status: To Do
priority: Low
until: 
project: GTRR

Total: 4
Complete: 0
Incomplete: 4
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
## Descrição
Estudar e criar temas baseados no guia de estilos da GTRR

## Tasks
- [ ] Estudar como criar temas do Obsidian
- [ ] Realizar testes
- [ ] Criar tema
- [ ] Disponibilizar
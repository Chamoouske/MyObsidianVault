---
status: In Progress
priority: High
until: 
project: GTRR

Total: 14
Complete: 8
Incomplete: 6
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
Desenvolvimento do site da GTRR

## Tasks
- [x] Homepage
- [x] Primeiros Passos
- [ ] Sobre
	- [ ] Manifesto
	- [ ] Estatuto
- [x] FAQ
- [x] Sugestão de Projetos
- [x] Cadastro
	- [x] Camaradas
	- [x] Membros
- [ ] Projetos
	- [ ] Andamento
	- [ ] Finalizados
- [x] DNS
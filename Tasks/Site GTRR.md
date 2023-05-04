---

status: In Progress
priority: High
until: 
project: GTRR

Total: 13
Complete: 7
Incomplete: 6

---
```dataviewjs
const {update} = this.app.plugins.plugins['metaedit'].api;

(async () => {
	const tasks = dv.current().file.tasks;
	const completedTasks = tasks.where(t=>t.completed).length;
	const incompletedTasks = tasks.where(t=>!t.completed).length;
	
	await update('Total', tasks.length, dv.current().file.path)
	await update('Complete', completedTasks, dv.current().file.path)
	await update('Incomplete', incompletedTasks, dv.current().file.path)
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
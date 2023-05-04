---

status: Completed
priority: Low
until: 2023-05-06
project: Teste

Total: 1
Complete: 1
Incomplete: 0

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


## Tasks
- [x]  
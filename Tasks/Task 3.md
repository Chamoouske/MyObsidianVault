---

status: To Do
priority: Low
until: 2023-05-16
project: Teste

Total: 4
Complete: 2
Incomplete: 2

---
```dataviewjs
const {update} = this.app.plugins.plugins['metaedit'].api;

(async () => {
	/*const tasks = dv.current().file.tasks;
	const completedTasks = tasks.where(t=>t.completed).length;
	const incompletedTasks = tasks.where(t=>!t.completed).length;
	
	await update('Total', tasks.length, dv.current().file.path)
	await update('Complete', completedTasks, dv.current().file.path)
	await update('Incomplete', incompletedTasks, dv.current().file.path)*/
})()

for(let checkbox of document.querySelectorAll('.task-list-item-checkbox')){
	checkbox.addEventListener('click', ()=>{console.log(teste)})
}
```
## Description


## Tasks
- [ ]  
- [ ]  
- [ ]  
- [x]  
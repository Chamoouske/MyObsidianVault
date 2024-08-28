---
tags:
  - cursos
url: 
finalizado: true
title: 
quantidade-modulos: 1
---

```dataviewjs
const { update } = this.app.plugins.plugins['metaedit'].api;

(async function updatePercentTasks(){
	const tasks = dv.current().file.tasks;
	const completedTasks = tasks.where(t=>t.completed).length;
	const incompletedTasks = tasks.where(t=>!t.completed).length;
	
	if(tasks.length != dv.current().Total)
		await update('Total_Modulos', tasks.length, dv.current().file.path);
	if(completedTasks != dv.current().Complete)
		await update('Modulos_Finalizados', completedTasks, dv.current().file.path);
	if(incompletedTasks != dv.current().Incomplete)
		await update('Modulos_Faltantes', incompletedTasks, dv.current().file.path);
})()
```
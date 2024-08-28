---
tags:
  - cursos
url: 
finalizado: false
title: 
Total_Modulos: 0
Modulos_Finalizados: 0
Modulos_Faltantes: 0

---
<%*
const { update } = this.app.plugins.plugins['metaedit'].api;

let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = (await tp.system.prompt("Nome do Anime: ")).replace(re, '_');
}
const pathCurso = `Cursos/Andamento/${title}`;
await tp.file.move(`${pathCurso}/${title}`);

//const totalModulos = await tp.system.prompt("Total de módulos: ") || 0;
await update('Total_Modulos', await tp.system.prompt("Total de módulos: ") || 0, dv.current().file.path);
%>

---
```dataviewjs
let pages = await dv.pages(`<% pathCurso %>/Modulos`);
```
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
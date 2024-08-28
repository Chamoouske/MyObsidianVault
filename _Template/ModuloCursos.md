<%*
const { update } = this.app.plugins.plugins['metaedit'].api;

let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.contains("Untitled") || title.contains("Sem título")){
	title = (await tp.system.prompt("Título do Módulo: ")).replace(re, '_');
}

await tp.file.rename(title);
%>---
finalizado: false
total_aulas: 0
---

---
- [ ] Aula 1
---
```dataviewjs
const { update } = this.app.plugins.plugins['metaedit'].api;

(async function updatePercentTasks() {
	const tasksModulos = dv.current().file.tasks;
	const completedTasks = tasksModulos.where(t=>t.completed).length;
	const incompletedTasks = tasksModulos.where(t=>!t.completed).length;
	
	if(tasksModulos.length != dv.current().total_aulas)
		await update('Total_Modulos', tasksModulos.length, dv.current().file.path);
	if(completedTasks != dv.current().Modulos_Finalizados)
		await update('Modulos_Finalizados', completedTasks, dv.current().file.path);
	if(incompletedTasks != dv.current().Modulos_Faltantes)
		await update('Modulos_Faltantes', incompletedTasks, dv.current().file.path);
	if(tasksModulos.length == dv.current().total_aulas && !dv.current().finalizado)
		await update('finalizado', true, dv.current().file.path);
})()
```
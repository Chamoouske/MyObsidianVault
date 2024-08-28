<%*
const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');

let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = (await tp.system.prompt("Nome do Anime: ")).replace(re, '_');
}

const pathCurso = `Cursos/Andamento/${title}`;
await tp.file.move(`${pathCurso}/${title}`);

const totalModulos = await tp.system.prompt("Total de módulos: ") || 0;

for(let i = 0; i < totalModulos; i++) await createNewNoteTemplater(findTFileTemplater('ModuloCursos'), `${pathCurso}/${title}/Modulos/Untitled`, true);
%>---
tags:
  - cursos
url: 
finalizado: false
title: <% title %>
Total_Modulos: <% totalModulos %>
Modulos_Finalizados: 0
Modulos_Faltantes: 0
---

---
```dataviewjs
const pages = await dv.pages(`"<% pathCurso %>/Modulos"`);

dv.taskList(pages.file.tasks.filter(task=> task.children = []));
```
---
```dataviewjs
const { update } = this.app.plugins.plugins['metaedit'].api;
const tasksModulos = await dv.pages(`"${dv.current().file.folder}/Modulos"`).file.tasks;

(async function updatePercentTasks() {
	const completedTasks = tasksModulos.where(t=>t.completed).length;
	const incompletedTasks = tasksModulos.where(t=>!t.completed).length;
	
	if(tasksModulos.length != dv.current().Total_Modulos)
		await update('Total_Modulos', tasksModulos.length, dv.current().file.path);
	if(completedTasks != dv.current().Modulos_Finalizados)
		await update('Modulos_Finalizados', completedTasks, dv.current().file.path);
	if(incompletedTasks != dv.current().Modulos_Faltantes)
		await update('Modulos_Faltantes', incompletedTasks, dv.current().file.path);
		
	setTimeout(updatePercentTasks, 5000);
})()
```
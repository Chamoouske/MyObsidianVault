<%*
const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');
const suggester = tp.system.suggester;

let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = (await tp.system.prompt("Nome do Curso: ")).replace(re, '_');
}

const pathCurso = `Cursos/Andamento/${title}`;
await tp.file.move(`${pathCurso}/${title}`);

const status = "To Do";

const prioridade = await suggester(
	["Low", "Moderate", "High", "Imediate"],
	["Low", "Moderate", "High", "Imediate"],
	false,
	"Prioridade"
) || "Low";

const totalModulos = await tp.system.prompt("Total de módulos: ") || 0;

for(let i = 0; i < totalModulos; i++) await createNewNoteTemplater(findTFileTemplater('ModuloCursos'), `${pathCurso}/Modulos/Untitled`, false);
%>---
tags:
  - cursos
url: <% await tp.system.prompt("URL do Curso: ") || '' %>
finalizado: false
title: <% title %>
Total_Modulos: <% totalModulos %>
Modulos_Finalizados: 0
Modulos_Faltantes: <% totalModulos %>
status: <% status %>
priority: <% prioridade %>
---
<% tp.file.cursor() %>
---
```dataviewjs
const {createButton} = app.plugins.plugins["buttons"];
const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');

createButton({
	app,
	el: this.container,
	args: {name: "Novo Módulo"},
	clickOverride: {
		click: createNewNoteTemplater,
		params: [
			findTFileTemplater('ModuloCursos'), '<% pathCurso %>/Modulos/Untitled', true
		]
	}
});

function createDivPercentage(percent){
	let style = `
		width:100%;
		border:1px solid green;
		text-align:center;
		border-radius:0.7rem;
		background-image:linear-gradient(to right, rgb(0,130,0,1) ${percent<100?percent-10:percent}%,rgb(0,130,0,0) ${percent<100?percent+20:0}%);`;
	return `<div style="${style}">${percent}%</div>`
}

const pages = await dv.pages(`"<% pathCurso %>/Modulos"`);

dv.table(['Módulo', 'Progress'],
	pages.sort(t=>-((t.Modulos_Finalizados / t.Total_Modulos || 0) * 100))
		.map(t => {
			const tasks = t.file.tasks;
			const completed = tasks.where(t=>t.completed)
			const progress = ((completed.length / tasks.length || 0) * 100)
			return [
				t.file.link,
				createDivPercentage(progress.toFixed(2))
			]
		})
)
```
---
```dataviewjs
const { update } = this.app.plugins.plugins['metaedit'].api;

async function updateStatus() {
	let novoStatus = 'To Do';
	if(dv.current().Modulos_Finalizados == dv.current().Total_Modulos) {
		novoStatus = 'Finalizado';
		await update('finalizado', true, dv.current().file.path);
	}
	if(dv.current().Modulos_Finalizados != dv.current().Total_Modulos && dv.current().Modulos_Faltantes != dv.current().Total_Modulos)
		novoStatus = 'Andamento';

	if(novoStatus != dv.current().status)
		await update('status', novoStatus, dv.current().file.path);
}

(async function updatePercentTasks() {
	const tasksModulos = await dv.pages(`"${dv.current().file.folder}/Modulos"`);
	const completedTasks = tasksModulos.where(t=>t.completed).length;
	const incompletedTasks = tasksModulos.where(t=>!t.completed).length;
	
	if(tasksModulos.length != dv.current().Total_Modulos)
		await update('Total_Modulos', tasksModulos.length, dv.current().file.path);
	if(completedTasks != dv.current().Modulos_Finalizados)
		await update('Modulos_Finalizados', completedTasks, dv.current().file.path);
	if(incompletedTasks != dv.current().Modulos_Faltantes)
		await update('Modulos_Faltantes', incompletedTasks, dv.current().file.path);

	await updateStatus();
})()
```

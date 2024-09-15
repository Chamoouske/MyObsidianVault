---
tags:
  - cursos
url: https://app.algaworks.com/meus-cursos/especialista-java
finalizado: false
title: Especialista Java
Total_Modulos: 35
Modulos_Finalizados: 28
Modulos_Faltantes: 7
status: Andamento
priority: High

---

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
			findTFileTemplater('ModuloCursos'), 'Cursos/Andamento/Especialista Java/Modulos/Untitled', true
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

function definePercentProgressionByDataviewPage(page) {
	const tasks = page.file.tasks;
	const completed = tasks.where(t => t.completed)

	return ((completed.length / tasks.length) || 0) * 100
}

const pages = await dv.pages(`"Cursos/Andamento/Especialista Java/Modulos"`);

dv.table(['Módulo', 'Progress'],
	pages.filter(t => !t.completed)
		.sort(t => {
			return - 1 * definePercentProgressionByDataviewPage(t);
		}).map(t => {
			return [
				t.file.link,
				createDivPercentage(
					definePercentProgressionByDataviewPage(t).toFixed(2)
				)
			]
		})
)
```
---
```dataviewjs
const { update } = this.app.plugins.plugins['metaedit'].api;

async function updateStatus() {
	let novoStatus = 'To Do';
	if(dv.current().Modulos_Finalizados == dv.current().Total_Modulos)
		novoStatus = 'Finalizado';
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

---
banner: "https://images5.alphacoders.com/750/750261.png"
banner_y: 0.332
banner_x: 0.5
---

## [[Animes]]
```button
name Add Anime
type note(Animes/TemporadaAtual/Untitled, split) template
action AnimeTempAtual
templater true
```
```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
let pages= dv.pages(`"Animes/TemporadaAtual" AND #${dv.pages('"Animes/Animes"')[0].anime_season}`);

const today = new Date().toLocaleString('en', { weekday: 'long' });

dv.header(4, 'Today')
dv.table(['Nome', 'Último EP', '', ''],
	 pages.where(item => !item.dropped && !item.finished && item.on_air==today)
		 .sort(a=>a.last_episode)
		 .map(anime=>[
			anime.file.link,
			anime.last_episode,
			createButton({
				app,
				el: this.container,
				args: {name: "+1 ep"},
				clickOverride: {
					click: update,
					params: [
						'last_episode', anime.last_episode + 1,
						anime.file.path
					]
				}
			})
		]
))
```

## Tasks
```button
name Add Task
type note(Untitled) template
action NewMainTaskGTRR
templater true
```
```dataviewjs
const {createButton} = app.plugins.plugins['buttons'];
const {update} = this.app.plugins.plugins['metaedit'].api;
const prompt = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[4].static_functions.get('prompt');

function createDivPercentage(percent){
	let style = `
		width:100%;
		border:1px solid green;
		text-align:center;
		border-radius:0.7rem;
		background-image:linear-gradient(to right, rgb(0,130,0,1) ${percent<100?percent-10:percent}%,rgb(0,130,0,0) ${percent<100?percent+20:0}%);`;
	return `<div style="${style}">${percent}%</div>`
}

async function updatePercentTasks(file){
	const tasks = file.file.tasks;
	const completedTasks = tasks.where(t=>t.completed).length;
	const incompletedTasks = tasks.where(t=>!t.completed).length;
	
	if(tasks.length != file.Total)
		await update('Total', tasks.length, file.file.path);
	if(completedTasks != file.Complete)
		await update('Complete', completedTasks, file.file.path);
	if(incompletedTasks != file.Incomplete)
		await update('Incomplete', incompletedTasks, file.file.path);
}

async function setDueDate(path){
	const date = await prompt('Set Due Date');
	if(date){
		const newDate = app.plugins.plugins['nldates-obsidian'].parseDate(date).moment.format("YYYY-MM-DD");
		await update('until', newDate, path)
	}
}

const pages = dv.pages('"Tasks"');
for(let group of ['GTRR', 'Personal', 'Other']){
	dv.header(4, group)
	dv.table(
		['Task', 'Status', 'Priority', 'Due Date', 'Progress', ''],
		pages.sort(t=>((t.Complete / t.Total || 0) * 100))
			.where(t=>!(t.status=='Completed') && t.project == group)
			.map(t => {
				const daysRemaining = (new Date(t.until) - new Date()) / (1000 * 60 * 60 * 24);
				let color;
				if(daysRemaining < 1){
					color = "red";
				}else if(daysRemaining < 4){
					color = "purple";
				}else{
					color = "green";
				}
				const tasks = t.file.tasks;
				const completed = tasks.where(t=>t.completed)
				const progress = ((completed.length / tasks.length || 0) * 100)
				return [
					t.file.link,
					t.status,
					t.priority,
					t.until || createButton({
							app,
							el: this.container,
							args: {name: "Set Date"},
							clickOverride: {
								click: setDueDate,
								params: [
									t.file.path
								]
							}
						}),
					createDivPercentage(progress.toFixed(2)),
					createButton({
						app,
						el: this.container,
						args: {
							name: t.status == "To Do" ? "In Progress" : " Complete ",
							color: t.until ? color : "green"
						},
						clickOverride: {
							click: update,
							params: [
								'status',
								t.status == "To Do" ? "In Progress" : "Completed",
								t.file.path
							]
						}
					})
				]
			})
	)
}

dv.header(4, "All Tasks")
dv.table(
	['Task', 'Project', 'Status', 'Priority', 'Progress'],
	pages.sort(t=>((t.Complete / t.Total || 0) * 100))
		.map(t => {
				const progress = ((t.Complete / t.Total || 0) * 100)
				updatePercentTasks(t)
				return [
					t.file.link,
					t.project,
					t.status,
					t.priority,
					createDivPercentage(progress.toFixed(2))
				]
			}
		)
)
```

## Vídeos
```button
name Add Vídeo
type note(Untitled) template
action AddIndicaçãoYoutube
templater true
```
```dataviewjs
const {createButton} = app.plugins.plugins['buttons'];
const {update} = this.app.plugins.plugins['metaedit'].api;

dv.table(
	['Title', 'Link', ''],
	dv.pages('"Youtube"')
		.where(t=>!t.watched)
		.map(video => [
			video.file.link,
			`<a href="${video.url}">Here</a>`,
			createButton({
				app,
				el: this.container,
				args: {name: "Watched"},
				clickOverride: {
					click: update,
					params: [
						'watched',
						true,
						video.file.path
					]
				}
			})
		])
)
```

## Guias de Ajuda
```dataview
LIST
FROM "Ajuda" and #Ajuda
```

## Guia de Estudos
```button
name Novo Guia da Estudos
type note(Untitled) template
action Guia_estudos
templater true
```
```dataviewjs
function createDivPercentage(percent){
	let style = `
		width:100%;
		border:1px solid green;
		text-align:center;
		border-radius:0.7rem;
		background-image:linear-gradient(to right, rgb(0,130,0,1) ${percent<100?percent-10:percent}%,rgb(0,130,0,0) ${percent<100?percent+20:0}%);`;
	return `<div style="${style}">${percent}%</div>`
}
const pages = dv.pages('"Guias de Estudo" AND !#kanban');

for(let group of pages.groupBy(t=>t.subject)){
	dv.header(4, group.key);
	dv.table(
		['Content', 'Progress', 'N Tasks', 'Incompleted'],
		group.rows.sort(t=>t.file.link)
			.map(item => {
				const tasks = item.file.tasks;
				const completedTasks = item.file.tasks.where(t=>t.completed).length
				return [
					item.file.link,
					createDivPercentage((completedTasks * 100 / tasks.length || 0).toFixed(2)),
					tasks.length,
					tasks.length - completedTasks
				]
			})
	)
}
```

## Roteiros
```dataview
LIST
FROM "Roteiros" and #roteiros
```

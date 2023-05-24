
---
banner: "https://images5.alphacoders.com/750/750261.png"
banner_y: 0.36
---
# [[Animes]]
```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');

createButton({
	app,
	el: this.container,
	args: {name: "Novo Anime"},
	clickOverride: {
		click: createNewNoteTemplater,
		params: [
			findTFileTemplater('AnimeTempAtual'), 'Untitled', true
		]
	}
})

let pages = await dv.pages(`"Animes/TemporadaAtual" AND #${dv.pages('"Animes/Animes"')[0]?.anime_season}`);

let now = new Date(new Date().setHours(0, 0, 0, 0));
function equalDates(date){
	date = new Date(`${date.year}-${date.month}-${date.day}`);
	return now.getTime() === date.getTime();
}
async function defer(key, value, file){
	await update(key, value, file);
	if (key === 'last_episode'){
		let month = `${now.getMonth() + 1}`;
		if (month.length < 2) month = `0${month}`;
		let day = `${now.getDate()}`;
		if (day.length < 2) day = `0${day}`;

		await update('last_watch', `${now.getFullYear()}-${month}-${day}`, file);
	}
}

let year = `${now.getFullYear()}`;
let month = `${now.getMonth() + 1}`;
if (month.length < 2) month = `0${month}`;
let day = `${now.getDate()}`;
if (day.length < 2) day = `0${day}`;

const today = now.toLocaleString('en', { weekday: 'long' });
dv.header(2, 'Today')
dv.table(['Nome', 'Último EP', "Gêneros", ''],
	 pages.where(item => !item.dropped && !item.finished && item.on_air==today && !equalDates(item.last_watch))
		 .sort(a=>a.name)
		 .map(anime=>{
			 return [
				anime.file.link,
				anime.last_episode,
				anime.genre,
				createButton({
					app,
					el: this.container,
					args: {name: "+1 ep"},
					clickOverride: {
						click: defer,
						params: [
							'last_episode', anime.last_episode + 1,
							anime.file.path
						]
					}
				})
			]
		}
	)
)
```

# Filmes
```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];

const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');

createButton({
	app,
	el: this.container,
	args: {name: "Novo Filme"},
	clickOverride: {
		click: createNewNoteTemplater,
		params: [
			findTFileTemplater('NewFilme'), 'Untitled', true
		]
	}
})

let pages = await dv.pages(`"Filmes"`);
dv.table(['Título', 'Indicou', 'Adicionado', ''],
	 pages.where(item => !item.Assistido)
		 .sort(a=>a.Added)
		 .map(filme=>[
			filme.file.link,
			filme['Indicado-por'],
			filme.Added,
			createButton({
				app,
				el: this.container,
				args: {name: "Assistido"},
				clickOverride: {
					click: update,
					params: [
						'Assistido', true,
						filme.file.path
					]
				}
			})
		]
))
```

# Livros
```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');

createButton({
	app,
	el: this.container,
	args: {name: "Novo Livro"},
	clickOverride: {
		click: createNewNoteTemplater,
		params: [
			findTFileTemplater('NewLivro'), 'Untitled', true
		]
	}
})

let pages = await dv.pages(`"Livros"`);
dv.table(['Título', 'Adicionado',  ''],
	 pages.where(item => !item.Lido)
		 .sort(a=>a.Added)
		 .map(filme=>[
			filme.file.link,
			filme.Added,
			createButton({
				app,
				el: this.container,
				args: {name: "Lido"},
				clickOverride: {
					click: update,
					params: [
						'Lido', true,
						filme.file.path
					]
				}
			})
		]
))
```

# Tasks
```dataviewjs
const {createButton} = app.plugins.plugins['buttons'];
const {update} = this.app.plugins.plugins['metaedit'].api;

const prompt = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[4].static_functions.get('prompt');
const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');

createButton({
	app,
	el: this.container,
	args: {name: "Nova Task"},
	clickOverride: {
		click: createNewNoteTemplater,
		params: [
			findTFileTemplater('Tasks'), 'Untitled', true
		]
	}
})

function createDivPercentage(percent){
	let style = `
		width:100%;
		border:1px solid green;
		text-align:center;
		border-radius:0.7rem;
		background-image:linear-gradient(to right, rgb(0,130,0,1) ${percent<100?percent-10:percent}%,rgb(0,130,0,0) ${percent<100?percent+20:0}%);`;
	return `<div style="${style}">${percent}%</div>`
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
	dv.header(2, group)
	dv.table(
		['Task', 'Status', 'Priority', 'Due Date', 'Progress', ''],
		pages.sort(t=>-((t.Complete / t.Total || 0) * 100))
			.where(t=>!(t.status=='Completed') && t.project == group)
			.map(t => {
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
							name: t.status == "To Do" ? "In Progress" : " Complete "
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

dv.header(2, "All Tasks")
dv.table(
	['Task', 'Project', 'Status', 'Progress'],
	pages.sort(t=>(-(t.Complete / t.Total || 0) * 100))
		.map(t => {
				const progress = ((t.Complete / t.Total || 0) * 100)
				return [
					t.file.link,
					t.project,
					t.status,
					createDivPercentage(progress.toFixed(2))
				]
			}
		)
)
```

# Vídeos
```dataviewjs
const {createButton} = app.plugins.plugins['buttons'];
const {update} = this.app.plugins.plugins['metaedit'].api;
const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');

createButton({
	app,
	el: this.container,
	args: {name: "Nova Vìdeo"},
	clickOverride: {
		click: createNewNoteTemplater,
		params: [
			findTFileTemplater('VideosYoutube'), 'Untitled', false
		]
	}
})

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

# Guia de Estudos
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
const {createButton} = app.plugins.plugins['buttons'];
const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');

createButton({
	app,
	el: this.container,
	args: {name: "Nova Guia de Estudos"},
	clickOverride: {
		click: createNewNoteTemplater,
		params: [
			findTFileTemplater('GuiaEstudos'), 'Untitled', false
		]
	}
})
const pages = dv.pages('"Guias de Estudo" AND !#kanban');

for(let group of pages.groupBy(t=>t.subject)){
	dv.header(2, group.key);
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

# Guias de Ajuda
```dataview
LIST
FROM "Ajuda" and #Ajuda
```

# Roteiros
```dataview
LIST
FROM "Roteiros" and #roteiros
```

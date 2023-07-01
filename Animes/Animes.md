---
---
# Temporada Atual
```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];

const createNewNoteTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('create_new');
const findTFileTemplater = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('find_tfile');
const move = this.app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('move');

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

const date = new Date(Date.now())
let temp;
switch(date.getMonth() + 1){
	case 1:
	case 2:
	case 3:
		temp = 'Winter-' + date.getFullYear();
		break;
	case 4:
	case 5:
	case 6:
		temp = 'Spring-' + date.getFullYear();
		break;
	case 7:
	case 8:
	case 9:
		temp = 'Summer-' + date.getFullYear();
		break;
	case 10:
	case 12:
	case 12:
		temp = 'Fall-' + date.getFullYear();
		break;
}

createButton({
	app,
	el: this.container,
	args: {name: "Update Season"},
	clickOverride: {
		click: update,
		params: [
			'anime_season', temp,
			dv.current().file.path
		]
	}
})

let pages= dv.pages(`"Animes/TemporadaAtual"`);

async function defer(key, value, file){
	await update(key, value, file.path);
	if((key === 'dropped' && value) || (key === 'finished' && value)){
		await move(`Animes/Histórico/${key.replace(key[0], key[0].toUpperCase())}/${file.name}`, {...file, extension: 'md'});
	}else if (key === 'last_episode'){
		const date = new Date();
		let year = `${date.getFullYear()}`;
		let month = `${date.getMonth() + 1}`;
		if (month.length < 2) month = `0${month}`;
		let day = `${date.getDate()}`;
		if (day.length < 2) day = `0${day}`;

		const newDate = `${year}-${month}-${day}`;
		await update('last_watch', newDate, file.path);
	}
}

dv.header(2, 'Não dropados')
for(let group of ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday']){
	dv.header(3, group)
	dv.table(['Nome', 'Último EP', 'Gêneros', 'Assistido', ''],
		 pages.where(item => !item.dropped && !item.finished && item.on_air==group)
			 .sort(a=>a.name)
			 .map(anime=>[
				anime.file.link,
				anime.last_episode,
				anime.genre,
				anime.last_watch,
				[
					createButton({
						app,
						el: this.container,
						args: {name: anime.dropped ? "Reassistir" : "Drop"},
						clickOverride: {
							click: defer,
							params: [
								'dropped', !anime.dropped,
								anime.file
							]
						}
					}),
					createButton({
						app,
						el: this.container,
						args: {name: "Finalizar"},
						clickOverride: {
							click: defer,
							params: [
								'finished', !anime.finished,
								anime.file
							]
						}
					}),
					createButton({
						app,
						el: this.container,
						args: {name: "+1 ep"},
						clickOverride: {
							click: defer,
							params: [
								'last_episode', anime.last_episode + 1,
								anime.file
							]
						}
					})
				]
			]
	))
}
```

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];

const move = this.app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('move');

let pages= dv.pages(`"Animes/Histórico/Dropped"`);

async function defer(key, value, file){
	await update(key, value, file.path);
	await move(`Animes/TemporadaAtual/${file.name}`, {...file, extension: 'md'});
}

dv.header(2, "Dropados");
dv.table(['Nome', 'Lançamento', 'Último EP', ''],
	 pages.where(item => item.dropped && !item.finished)
		 .sort(a=>a.on_air).map(anime=>[
			anime.file.link,
			anime.on_air,
			anime.last_episode,
			createButton({
				app,
				el: this.container,
				args: {name: anime.dropped ? "Reassistir" : "Drop"},
				clickOverride: {
					click: defer,
					params: [
						'dropped', !anime.dropped,
						anime.file
					]
				}
			})
		]
))
```

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
let pages = dv.pages(`"Animes" AND !"Animes/Animes"`);

dv.header(2, "Tudo");

for(let group of pages.groupBy(a=>a.season)){
	dv.header(3, group.key)
	dv.table(['Nome', 'Episódios', 'Gêneros', 'Dropped'],
		 group.rows
			 .sort(a=>a.name)
			 .map(anime=>[
				anime.file.link,
				anime.last_episode,
				anime.genre,
				anime.dropped ? "Yes" : "No"
			]
	))
}
```

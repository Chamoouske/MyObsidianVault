---
tag: animes Spring-2023
name: Watashi no Yuri wa Oshigoto Desu
on_air: Thursday
last_episode: 5
season: Spring-2023
dropped: false
finished: false
created_at: 2023-04-27 13:48
---
## Gênero

## Resumo

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];

async function moveNoteToHistorico(){
	await app.plugins.plugins['templater-obsidian'].templater.current_functions_object.file.move(`Animes/Histórico/<% title.replace(re, '_') %>`)
}

async function defer(key, value, file){
	await update(key, value, file)
	await moveNoteToHistorico()
}

dv.header(3, "Último episódio assistido: `$= dv.current()?.last_episode`");
createButton({
	app,
	el: this.container,
	args: {name: "+1 ep"},
	clickOverride: {
		click: update,
		params: [
			'last_episode', dv.current()?.last_episode + 1,
			dv.current()?.file.path
		]
	}
})
createButton({
	app,
	el: this.container,
	args: {name: "-1 ep"},
	clickOverride: {
		click: update,
		params: [
			'last_episode', dv.current()?.last_episode - 1,
			dv.current()?.file.path
		]
	}
})
createButton({
	app,
	el: this.container,
	args: {name: dv.current()?.dropped ? "Reassistir" : "Drop"},
	clickOverride: {
		click: defer,
		params: [
			'dropped', !dv.current()?.dropped,
			dv.current()?.file.path
		]
	}
})
createButton({
	app,
	el: this.container,
	args: {name: "Finished"},
	clickOverride: {
		click: defer,
		params: [
			'finished', !dv.current()?.finished,
			dv.current()?.file.path
		]
	}
})

createButton({
	app,
	el: this.container,
	args: {name: 'Mover para Histórico'},
	clickOverride: {
		click: moveNoteToHistorico,
		params: []
	}
})
```

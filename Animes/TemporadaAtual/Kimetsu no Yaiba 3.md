---
tag: animes Spring-2023
name: Kimetsu no Yaiba 3
on_air: Sunday
last_episode: 3
season: Spring-2023
dropped: false
finished: false
created_at: 2023-04-27 15:27
---
## Gênero

## Resumo

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];

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
		click: update,
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
		click: update,
		params: [
			'finished', !dv.current()?.finished,
			dv.current()?.file.path
		]
	}
})
```

```button
name Jogar pro Histórico
type prepend template
action MoveToHistóricoInAnime
templater true
color purple
```
^button-sdyp
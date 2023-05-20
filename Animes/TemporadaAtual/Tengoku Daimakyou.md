---
tag: animes Spring-2023
name: Tengoku Daimakyou

on_air: Saturday
season: Spring-2023
last_episode: 8
last_watch: 2023-05-20
genre: 
 - "#Mystery"
 - "#Sci-Fi"
 - "#Adventure"
 - "#Thriller"

dropped: false
finished: false

created_at: 2023-05-11

banner: ""
banner_y: 0
---
## Sinópse
In the year 2024, the world has collapsed. Grotesque monsters lurk amongst the ruins of Japan, while remaining people scrape together what they can to survive. Kiruko, an odd-job girl in Nakano, accepts a mysterious woman's dying wish to take a boy named Maru to a place called Heaven.

## [Wallpapers](https://wall.alphacoders.com/search.php?search=Tengoku+Daimakyou&lang=Portuguese)

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
const move = this.app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('move');

async function moveNoteToHistorico(){
	await move(`Animes/Histórico/Tengoku Daimakyou`, {...dv.current().file, extension: 'md'})
}

async function defer(key, value, file){
	await update(key, value, file);
	if((key === 'dropped' && value) || (key === 'finished' && value)){
		await moveNoteToHistorico();
	}else if (key === 'last_episode'){
		const dt = new Date(Date.now());
		let year = `${dt.getFullYear()}`;
		let month = `${dt.getMonth() + 1}`;
		if (month.length < 2) month = `0${month}`;
		let day = `${dt.getDate()}`;
		if (day.length < 2) day = `0${day}`;

		const newDate = `${year}-${month}-${day}`;
		await update('last_watch', newDate, file);
	}
}

dv.header(3, "Último episódio assistido: `$= dv.current()?.last_episode`");
createButton({
	app,
	el: this.container,
	args: {name: "+1 ep"},
	clickOverride: {
		click: defer,
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
		click: defer,
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

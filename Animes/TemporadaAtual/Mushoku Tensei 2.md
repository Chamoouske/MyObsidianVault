---
tag: animes Summer-2023
name: Mushoku Tensei 2

on_air: Sunday
season: Summer-2023
last_episode: 0
last_watch: 2023-07-04
genre: 
 - "#Adventure"
 - "#Drama"
 - "#Ecchi"
 - "#Fantasy"

dropped: false
finished: false

created_at: 2023-07-02

banner: ""
banner_y: 0
---
## Sinópse
The second season of _Mushoku Tensei: Isekai Ittara Honki Dasu_.  
Rudeus heads north with new friends and powers in search of adventure and those he once knew.

## [Wallpapers](https://wall.alphacoders.com/search.php?search=Mushoku+Tensei+2&lang=Portuguese)

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
const move = this.app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('move');

async function moveNoteToHistorico(path){
	await move(path)
}

async function defer(key, value, file){
	await update(key, value, file);
	if((key === 'dropped' && value) || (key === 'finished' && value)){
		await move(`Animes/Histórico/${key.replace(key[0], key[0].toUppercase())}/Mushoku Tensei 2`, {...dv.current().file, extension: 'md'});
	}else if (key === 'last_episode'){
		const date = new Date();
		let year = `${date.getFullYear()}`;
		let month = `${date.getMonth() + 1}`;
		if (month.length < 2) month = `0${month}`;
		let day = `${date.getDate()}`;
		if (day.length < 2) day = `0${day}`;

		const newDate = `${year}-${month}-${day}`;
		await update('last_watch', newDate, file);
	}else if(!((key === 'dropped' && value) || (key === 'finished' && value))){
		await move(`Animes/TemporadaAtual/Mushoku Tensei 2`, {...dv.current().file, extension: 'md'})
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
```

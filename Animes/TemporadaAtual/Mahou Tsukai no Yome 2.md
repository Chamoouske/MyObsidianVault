---
tag: animes Spring-2023
name: Mahou Tsukai no Yome 2

on_air: Thursday
season: Spring-2023
last_episode: 8
last_watch: 2023-05-25
genre: 
 - "#Drama"
 - "#Fantasy"

dropped: false
finished: false

created_at: 2023-05-11

banner: "https://images3.alphacoders.com/880/880728.jpg"
banner_y: 0.164
---
## Sinópse
The second season of _Mahoutsukai no Yome_. Chise was able to accept Elias and herself, if not necessarily everything about her situation. After Cartaphilus fell back into a slumber that would not last forever, Chise was able to go back to her regular life. Then she receives an invitation from a mutual aid organization for mages called the College. Under the British Library exists a secret society of mages. Encounters and interactions with people are about to open some new doors. This is a story about saving yourself to save another.

## [Wallpapers](https://wall.alphacoders.com/search.php?search=Mahou+Tsukai+no+Yome+2&lang=Portuguese)

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
const move = this.app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('move');

async function moveNoteToHistorico(){
	await move(`Animes/Histórico/Mahou Tsukai no Yome 2`, {...dv.current().file, extension: 'md'})
}

async function defer(key, value, file){
	await update(key, value, file);
	if((key === 'dropped' && value) || (key === 'finished' && value)){
		await moveNoteToHistorico();
	}else if (key === 'last_episode'){
		const date = new Date();
		let year = `${date.getFullYear()}`;
		let month = `${date.getMonth() + 1}`;
		if (month.length < 2) month = `0${month}`;
		let day = `${date.getDate()}`;
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

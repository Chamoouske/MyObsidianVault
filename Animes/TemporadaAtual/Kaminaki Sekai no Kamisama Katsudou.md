---
tag: animes Spring-2023
name: Kaminaki Sekai no Kamisama Katsudou

on_air: Wednesday
season: Spring-2023
last_episode: 7
last_watch: 2023-05-17
genre: 
 - "#Action"
 - "#Comedy"

dropped: false
finished: false

created_at: 2023-05-11

banner: ""
banner_y: 0
---
## Sinópse
As heir to a cult leader, Yukito centers his life around the mysterious goddess Mitama. But everything changes after he’s killed during a ritual gone wrong. To his surprise, Yukito is reborn into a world with no concept of god! And in this world, life and death are decided by the Imperial State. As Yukito fights to protect his new village, someone from his past life lends a helping hand.

## [Wallpapers](https://wall.alphacoders.com/search.php?search=Kaminaki+Sekai+no+Kamisama+Katsudou&lang=Portuguese)

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
const move = this.app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('move');

async function moveNoteToHistorico(){
	await move(`Animes/Histórico/Kaminaki Sekai no Kamisama Katsudou`, {...dv.current().file, extension: 'md'})
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

		await update('last_watch', `${year}-${month}-${day}`, file);
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

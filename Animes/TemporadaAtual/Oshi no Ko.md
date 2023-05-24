---
tag: animes Spring-2023
name: Oshi no Ko

on_air: Wednesday
season: Spring-2023
last_episode: 7
last_watch: 2023-05-24
genre: 
 - "#Drama"
 - "#Mystery"

dropped: false
finished: false

created_at: 2023-05-11

banner: "https://images2.alphacoders.com/131/1311144.jpeg"
banner_y: 0.436
---
## Sinópse
When a pregnant young starlet appears in Gorou Amemiya’s countryside medical clinic, the doctor takes it upon himself to safely (and secretly) deliver Ai Hoshino’s child so she can make a scandal-free return to the stage. But no good deed goes unpunished, and on the eve of her delivery, he finds himself slain at the hands of Ai’s deluded stalker — and subsequently reborn as Ai’s child, Aquamarine Hoshino! The glitz and glamor of showbiz hide the dark underbelly of the entertainment industry, threatening to dull the shine of his favorite star. Can he help his new mother rise to the top of the charts? And what will he do when unthinkable disaster strikes?

## [Wallpapers](https://wall.alphacoders.com/search.php?search=Oshi+no+Ko&lang=Portuguese)

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
const move = this.app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[1].static_functions.get('move');

async function moveNoteToHistorico(){
	await move(`Animes/Histórico/Oshi no Ko`, {...dv.current().file, extension: 'md'})
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

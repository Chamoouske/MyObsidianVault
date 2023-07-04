---
tag: animes Summer-2023
name: Suki na Ko ga Megane wo Wasureta

on_air: Tuesday
season: Summer-2023
last_episode: 1
last_watch: 2023-07-04
genre: 
 - "#Comedy"
 - "#Romance"

dropped: false
finished: false

created_at: 2023-07-04

banner: ""
banner_y: 0
---
## Sinópse
With the new school year comes a new homeroom, new classmates, and a new desk for the timid Komura. But any trepidation he might've felt quickly dissipates when he catches sight of Mie, his new seat neighbor. Apt to quietly blurt out the most random things, the quirky Mie wears thick glasses that accentuate her lovely eyes, making Komura’s heart skip a beat!  
  
Unfortunately, Mie is pathologically forgetful and can never seem to remember to bring her glasses to class. It's not all bad, though! Her resulting squinty, mean-girl face sends Komura’s heart into overdrive too! While Komura is keen to help out and share his textbooks with Mie, will his heart give out from the almost daily strain of being up close and personal with his crush?!

## [Wallpapers](https://wall.alphacoders.com/search.php?search=Suki+na+Ko+ga+Megane+wo+Wasureta&lang=Portuguese)

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
		await move(`Animes/Histórico/${key.replace(key[0], key[0].toUpperCase())}/Suki na Ko ga Megane wo Wasureta`, {...dv.current().file, extension: 'md'});
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
		await move(`Animes/TemporadaAtual/Suki na Ko ga Megane wo Wasureta`, {...dv.current().file, extension: 'md'})
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

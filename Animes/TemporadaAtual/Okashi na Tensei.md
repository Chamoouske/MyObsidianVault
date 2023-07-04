---
tag: animes Summer-2023
name: Okashi na Tensei

on_air: Monday
season: Summer-2023
last_episode: 0
last_watch: 2023-07-04
genre: 
 - "#Action"
 - "#Fantasy"
 - "#Slice_of_Life"

dropped: false
finished: false

created_at: 2023-07-04

banner: ""
banner_y: 0
---
## Sinópse
A boy named Pastry is set to become the next lord of the destitute dominion of Morteln. He's known for having remarkable talent for his age... and it just so happens he was a genius pastry chef with a promising future in his previous life! He still retains his determination to make sweets that will make everyone smile, even after reincarnating as Pastry. But many challenges stand before him, including bandits attacking his domain, malicious and eccentric nobles, an unfortunate financial situation, and land so barren that even water is scarce. The only weapons he has to fight them with are his own ingenuity and love for making sweets. Can Pastry succeed in bringing happiness to the land?!

## [Wallpapers](https://wall.alphacoders.com/search.php?search=Okashi+na+Tensei&lang=Portuguese)

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
		await move(`Animes/Histórico/${key.replace(key[0], key[0].toUppercase())}/Okashi na Tensei`, {...dv.current().file, extension: 'md'});
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
		await move(`Animes/TemporadaAtual/Okashi na Tensei`, {...dv.current().file, extension: 'md'})
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

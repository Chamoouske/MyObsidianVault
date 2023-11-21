---
tag: animes Summer-2023
name: Yumemiru Danshi wa Genjitsushugisha

on_air: Tuesday
season: Summer-2023
last_episode: 2
last_watch: 2023-07-11
genre: 
 - "#Comedy"
 - "#Romance"
 - "#Slice_of_Life"

dropped: true
finished: false

created_at: 2023-07-04

banner: ""
banner_y: 0
---
## Sinópse
Sajou Wataru, who is deeply in love with his beautiful classmate Natsukawa Aika, is continuing to approach her without getting discouraged while having dreams about their mutual love. However one day he woke up thinking "I am not really fit to be together with someone as good as her, huh..." Upon realizing this, Wataru started keeping an appropriate distance towards her, much to Aika's surprise. "Could it be that he hates me now...?" Did his intentions slip by her because she was getting impatient after arriving at the wrong conclusion!? This is the start of a romcom revolving around two people who just cant get their feelings across and both think their love is unrequited!

## [Wallpapers](https://wall.alphacoders.com/search.php?search=Yumemiru+Danshi+wa+Genjitsushugisha&lang=Portuguese)

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
		await move(`Animes/Histórico/${key.replace(key[0], key[0].toUppercase())}/Yumemiru Danshi wa Genjitsushugisha`, {...dv.current().file, extension: 'md'});
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
		await move(`Animes/TemporadaAtual/Yumemiru Danshi wa Genjitsushugisha`, {...dv.current().file, extension: 'md'})
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

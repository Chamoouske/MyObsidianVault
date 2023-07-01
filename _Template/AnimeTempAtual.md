<%*
let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("Nome do Anime: ");
}
await tp.file.move('Animes/TemporadaAtual/' + title.replace(re, '_'));

const date = new Date(tp.file.creation_date());
const month = date.getMonth() + 1;
let season;
switch(month){
	case 1:
	case 2:
	case 3:
		season = 'Winter-' + date.getFullYear();
		break;
	case 4:
	case 5:
	case 6:
		season = 'Spring-' + date.getFullYear();
		break;
	case 7:
	case 8:
	case 9:
		season = 'Summer-' + date.getFullYear();
		break;
	case 10:
	case 11:
	case 12:
		season = 'Fall-' + date.getFullYear();
		break;
}
let on_air = await tp.system.suggester(["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"], ["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Saturday"], false, "Dia do lançamento: ")

let lastEpisode = await tp.system.prompt("Último ep assistido: ") || 0;

let banner = await tp.system.prompt("Link de um banner: ") || '';

const linkWallpapers = `[Wallpapers](https://wall.alphacoders.com/search.php?search=${title.replaceAll(' ', '+')}&lang=Portuguese)`;

let genres = await tp.system.prompt('Gêneros (separados por ","):') || '';
if (genres) {
	genres = genres.split(',');
	let aux = ''
	for (let genre of genres){
		genre = genre.replace(genre[0], genre[0].toUpperCase());
		aux += `
 - "#${genre.trim().replaceAll(' ', '_')}"`;
	}
	genres = aux;
}

let lastWatch = tp.file.last_modified_date('YYYY-MM-DD');
%>---
tag: animes <% season %>
name: <% title %>

on_air: <% on_air %>
season: <% season %>
last_episode: <% lastEpisode %>
last_watch: <% lastWatch %>
genre: <% genres %>

dropped: false
finished: false

created_at: <% tp.file.creation_date('YYYY-MM-DD') %>

banner: "<% banner %>"
banner_y: 0
---
## Sinópse


## <% linkWallpapers %>

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
		await move(`Animes/Histórico/${key.replace(key[0], key[0].toUppercase())}/<% title.replace(re, '_') %>`, {...dv.current().file, extension: 'md'});
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
		await move(`Animes/TemporadaAtual/<% title.replace(re, '_') %>`, {...dv.current().file, extension: 'md'})
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

<%*
let title = tp.file.title;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("File name: ");
	await tp.file.rename(title);
}

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
let on_air = await tp.system.suggester(["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Sunday"], ["Sunday","Monday","Tuesday","Wednesday","Thursday","Friday","Sunday"], false, "Dia do lançamento: ")

let lastEpisode = await tp.system.prompt("Último ep assistido: ") || 0;
let banner = await tp.system.prompt("Link de um banner: ") || '';
%>---

tag: animes <% season %>
name: <% title %>
on_air: <% on_air %>
last_episode: <% lastEpisode %>
season: <% season %>
dropped: false
finished: false
created_at: <% tp.file.creation_date() %>
banner: <% banner %>

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
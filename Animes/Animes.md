
---

anime_season: Spring-2023
banner: "https://images5.alphacoders.com/750/750261.png"

banner_y: 0.36
---
# Temporada Atual
```button
name Add Anime
type note(Animes/TemporadaAtual/Untitled, split) template
action AnimeTempAtual
templater true
```
```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];

const date = new Date(Date.now())
let temp;
switch(date.getMonth() + 1){
	case 1:
	case 2:
	case 3:
		temp = 'Winter-' + date.getFullYear();
		break;
	case 4:
	case 5:
	case 6:
		temp = 'Spring-' + date.getFullYear();
		break;
	case 7:
	case 8:
	case 9:
		temp = 'Summer-' + date.getFullYear();
		break;
	case 10:
	case 12:
	case 12:
		temp = 'Fall-' + date.getFullYear();
		break;
}

createButton({
	app,
	el: this.container,
	args: {name: "Update Season"},
	clickOverride: {
		click: update,
		params: [
			'anime_season', temp,
			dv.current().file.path
		]
	}
})
```
```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
let pages= dv.pages(`"Animes/TemporadaAtual" AND #${dv.current().anime_season}`);


dv.header(2, 'Não dropados')
for(let group of ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday']){
	dv.header(3, group)
	dv.table(['Nome', 'Último EP', '', ''],
		 pages.where(item => !item.dropped && !item.finished && item.on_air==group)
			 .sort(a=>a.last_episode)
			 .map(anime=>[
				anime.file.link,
				anime.last_episode,
				createButton({
					app,
					el: this.container,
					args: {name: anime.dropped ? "Reassistir" : "Drop"},
					clickOverride: {
						click: update,
						params: [
							'dropped', !anime.dropped,
							anime.file.path
						]
					}
				}),
				createButton({
					app,
					el: this.container,
					args: {name: "+1 ep"},
					clickOverride: {
						click: update,
						params: [
							'last_episode', anime.last_episode + 1,
							anime.file.path
						]
					}
				})
			]
	))
}
```

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
let pages= dv.pages(`#${dv.current().anime_season}`);

dv.header(2, "Dropados");
dv.table(['Nome', 'Lançamento', 'Último EP', ''],
	 pages.where(item => item.dropped && !item.finished)
		 .sort(a=>a.on_air).map(anime=>[
			anime.file.link,
			anime.on_air,
			anime.last_episode,
			createButton({
				app,
				el: this.container,
				args: {name: anime.dropped ? "Reassistir" : "Drop"},
				clickOverride: {
					click: update,
					params: [
						'dropped', !anime.dropped,
						anime.file.path
					]
				}
			})
		]
))
```

```dataviewjs
const {update} = this.app.plugins.plugins["metaedit"].api;
const {createButton} = app.plugins.plugins["buttons"];
let pages = dv.pages(`#animes`);

dv.header(2, "Tudo");

for(let group of pages.groupBy(a=>a.season)){
	dv.header(3, group.key)
	dv.table(['Nome', 'Episódios', 'Dropped'],
		 group.rows.sort(a=>a.name)
			 .map(anime=>[
				anime.file.link,
				anime.last_episode,
				anime.dropped ? "Yes" : "No"
			]
	))
}
```

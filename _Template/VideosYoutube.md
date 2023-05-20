<%*
let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("Título do vídeo: ");
}

let videoId = await tp.system.prompt("Link");
if(videoId.indexOf('v=') !== -1){
	videoId = videoId.split('v=')[1]
}else{
	videoId = videoId.split('.be/')[1]
}
let url = `"https://www.youtube.com/watch?v=${videoId}"`

await tp.file.move("Youtube/" + title.replace(re, "_"));
%>---
title: "<% title %>"
url: <% url %>
watched: false
---
```dataviewjs
const { update } = this.app.plugins.plugins["metaedit"].api;
const { createButton } = app.plugins.plugins["buttons"];

createButton({
	app,
	el: this.container,
	args: {name: !dv.current()?.Assistido ? "Assistido" : "Não assistido"},
	clickOverride: {
		click: update,
		params: [
			'Assistido',
			!dv.current()?.Assistido,
			dv.current().file.path
		]
	}
})
```
## Vídeo
<% tp.file.cursor() %>
<iframe src="https://www.youtube.com/embed/<% videoId %>?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

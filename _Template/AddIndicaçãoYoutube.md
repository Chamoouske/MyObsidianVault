<%*
let title = tp.file.title;
const re = /[^\w\s()']/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("Título do vídeo: ");
	await tp.file.rename(title.replace(re, "_"));
}

let videoId = await tp.system.prompt("Link");
if(videoId.indexOf('v=') !== -1){
	videoId = videoId.split('v=')[1]
}else{
	videoId = videoId.split('.be/')[1]
}

await tp.file.move("Youtube/" + title.replace(re, "_"))
%>---

title: "<% title %>"
url: "https://www.youtube.com/watch?v=<% videoId %>"
watched: false

---
## Vídeo
<% tp.file.cursor() %>
<iframe src="https://www.youtube.com/embed/<% videoId %>?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

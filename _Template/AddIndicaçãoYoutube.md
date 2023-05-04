<%*
let title = tp.file.title;
const re = /[^*\\/"<>:|?]+/g
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("Título do vídeo: ");
	console.log(reg.exec(title))
	await tp.file.rename(title.replace(re, "_"));
}

let link = await tp.system.prompt("Link");

await tp.file.move("Youtube/" + title.replace(re, "_"))
%>---

tag: vídeos
title: <% title %>
url: "<% link %>"
watched: false

---

<iframe src="<% link %>" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>
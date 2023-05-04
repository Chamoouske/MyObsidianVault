<%*
let title = tp.file.title;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("Título do vídeo: ");
	await tp.file.rename(title);
}

let link = await tp.system.prompt("Link");

await tp.file.move("Youtube/" + title)
%>---

tag: vídeos
title: <% title %>
url: "<% link %>"

---

<%*
let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = (await tp.system.prompt("Assunto: ")).replace(re, '_');
}
await tp.file.move('Ajuda/' + title);
%>---
tag: ajuda
---

<% tp.file.cursor() %>
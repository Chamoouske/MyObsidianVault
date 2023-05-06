<%*
let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("File name: ");
}
console.log(tp.file.folder())
console.log(tp.file.folder(true))
const subject = await tp.system.prompt("Subject: ") || 'Others';

await tp.file.move(`Guias de Estudo/Assuntos/${subject.replace(re, '_')}/${title.replace(re, '_')}`)
%>---

subject: <% subject %>

---
# <% title %>

- [ ] <% tp.file.cursor() %>

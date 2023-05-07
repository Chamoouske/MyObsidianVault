<%*
let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("File name: ");
	await tp.file.move('Guias de Estudo/Kanbans/' + title.replace(re, '_'))
}
%>---

tag: kanban <% await title %>
kanban-plugin: basic

---

## Estudar


## Estudando


## Revisar


## Tudo certo


**Concluído**


%% kanban:settings
```
{"kanban-plugin":"basic"}
```
%%
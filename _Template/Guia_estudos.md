<%*
let title = tp.file.title;
const re = /[^\w\s()']/g;
if (title.startsWith("Untitled")){
	title = await tp.system.prompt("File name: ");
	await tp.file.rename(title.replace(re, '_'));
}
%>---
tag: guia/estudo/<% await title %>
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
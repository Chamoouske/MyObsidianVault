<%*
let title = tp.file.title;
if (title.startsWith("Untitled")){
	title = await tp.system.prompt("File name: ");
	await tp.file.rename(title.replace(/[^*\\/"<>:|?]+/, ''));
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
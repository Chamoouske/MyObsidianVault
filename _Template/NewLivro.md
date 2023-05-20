<%*
let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("Nome do livro: ");
	await tp.file.move('Livros/' + title.replace(re, '_'))
}

const idioma = await tp.system.prompt("Idioma:") || '';
%>---
Titulo: <% title %>
Idioma: <% idioma %>
Lido: false
Added: <% tp.date.now() %>
---
```dataviewjs
const { update } = this.app.plugins.plugins["metaedit"].api;
const { createButton } = app.plugins.plugins["buttons"];

createButton({
	app,
	el: this.container,
	args: {name: !dv.current()?.Lido ? "Lido" : "Não lido"},
	clickOverride: {
		click: update,
		params: [
			'Lido',
			!dv.current()?.Lido,
			dv.current().file.path
		]
	}
})
```
## Descrição

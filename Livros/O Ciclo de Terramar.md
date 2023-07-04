---
Titulo: O Cilco de Terramar
Idioma: pt-BR
Lido: false
Added: 2023-05-21
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

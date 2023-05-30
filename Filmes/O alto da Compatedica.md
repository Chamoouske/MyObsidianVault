---
Titulo: O alto da Compatedica
Indicado-por: Eu
Assistido: false
Added: 2023-05-29
---
```dataviewjs
const { update } = this.app.plugins.plugins["metaedit"].api;
const { createButton } = app.plugins.plugins["buttons"];

createButton({
	app,
	el: this.container,
	args: {name: !dv.current()?.Assistido ? "Assistido" : "Não assistido"},
	clickOverride: {
		click: update,
		params: [
			'Assistido',
			!dv.current()?.Assistido,
			dv.current().file.path
		]
	}
})
```
## Sinópse

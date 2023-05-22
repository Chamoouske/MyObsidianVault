---
Titulo: SMACSS
Idioma: Inglês
Lido: false
Added: 2023-05-22
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
			dv.current()?.file.path
		]
	}
})
```
## Descrição
Livro sobre Arquiteturas escaláveis e modulares de CSS

Encontrado em: [Scalable and ModularArchitecture for CSS](http://smacss.com/book/)
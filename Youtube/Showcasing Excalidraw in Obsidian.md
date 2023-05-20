---
title: "Showcasing Excalidraw in Obsidian"
url: "https://www.youtube.com/watch?v=o0exK-xFP3k"
watched: false
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
## Vídeo

<iframe src="https://www.youtube.com/embed/o0exK-xFP3k?feature=oembed" height="113" width="200" allowfullscreen="" allow="fullscreen" style="aspect-ratio: 1.76991 / 1; width: 100%; height: 100%;"></iframe>

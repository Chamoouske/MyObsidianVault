---
salario: 1900
vr: 1600
restante-salario: 422.65
restante-vr: 360
---

```dataviewjs
const {createButton} = app.plugins.plugins["buttons"];
const {update} = this.app.plugins.plugins["metaedit"].api;
async function defer(key, value, file){
	await update(key, value > 0 ? value : 0, file);
}

createButton({
	app,
	el: this.container,
	args: {name: "Caiu salário"},
	clickOverride: {
		click: defer,
		params: [
			'restante-salario', parseInt(dv.current()['salario'] || 0) + parseInt(dv.current()['restante-salario'] || 0),
			dv.current()?.file.path
		]
	}
})
createButton({
	app,
	el: this.container,
	args: {name: "Caiu VR"},
	clickOverride: {
		click: defer,
		params: [
			'restante-vr', parseInt(dv.current()['vr'] || 0) + parseInt(dv.current()['restante-vr'] || 0),
			dv.current()?.file.path
		]
	}
})
```

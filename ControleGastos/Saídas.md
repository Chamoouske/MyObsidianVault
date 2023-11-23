---
celular: 260
parcela-celular: 8
material-alcie: 190
parcela-material-alcie: 4
spotify: 22
google-storage: 7
sapato-supermoda: 39
parcela-sapato-supermoda: 6
mochila-supermoda: 24
parcela-mochila-supermoda: 2
gastos-extras: 36.58
gastos-vr: 0
total-gastos-mes: 542
total-gastos: 3187.58
---

```dataviewjs
const {createButton} = app.plugins.plugins["buttons"];
const {update} = this.app.plugins.plugins["metaedit"].api;
async function defer(key, value, file){
	await update(key, value > 0 ? value : 0, file);
}

let totalDividas = 0;
totalDividas += parseFloat(dv.current()?.celular || 0) * (dv.current()['parcela-celular'] || 0);

totalDividas += parseFloat(dv.current()['material-alcie'] || 0) * (dv.current()['parcela-material-alcie'] || 0);

totalDividas += parseFloat(dv.current().spotify || 0);
totalDividas += parseFloat(dv.current()['google-storage'] || 0);

totalDividas += parseFloat(dv.current()['sapato-supermoda'] || 0) * (dv.current()['parcela-sapato-supermoda'] || 0);
totalDividas += parseFloat(dv.current()['mochila-supermoda'] || 0) * (dv.current()['parcela-mochila-supermoda'] || 0);

totalDividas += parseFloat(dv.current()['gastos-extras'] || 0);
if (parseFloat(totalDividas) != parseFloat(dv.current()['total-gastos'] || 0))
	await defer('total-gastos', totalDividas, dv.current().file.path);
	
let gastoMensal = 0;
gastoMensal += parseFloat((dv.current()['parcela-sapato-supermoda'] || 0) > 0 ? dv.current()['sapato-supermoda'] : 0);
gastoMensal += parseFloat((dv.current()['parcela-mochila-supermoda'] || 0) > 0 ? dv.current()['mochila-supermoda'] : 0);
gastoMensal += parseFloat((dv.current()['parcela-celular'] || 0) > 0 ? dv.current()['celular'] : 0);
gastoMensal += parseFloat((dv.current()['parcela-material-alcie'] || 0) > 0 ? dv.current()['material-alcie'] : 0);
gastoMensal += parseFloat(dv.current()['spotify'] || 0);
gastoMensal += parseFloat(dv.current()['google-storage'] || 0);
if (parseFloat(gastoMensal) != parseFloat(dv.current()['total-gastos-mes'] || 0))
	await defer('total-gastos-mes', gastoMensal, dv.current().file.path);

dv.header(2, `Total dividas: R$${totalDividas}`);
dv.header(2, `Spotify: R$${dv.current()['spotify']}`);
dv.header(2, `Google Storage: R$${dv.current()['google-storage']}`);
dv.header(2, `Gastos Extras: R$${dv.current()['gastos-extras']}`);
dv.header(2, `Gastos VR: R$${dv.current()['gastos-vr']}`);

dv.header(2, `Celular: R$${parseFloat(dv.current()['parcela-celular'] || 0) * parseFloat(dv.current()?.celular || 0)}`);
createButton({
	app,
	el: this.container,
	args: {name: "Pagou parcela"},
	clickOverride: {
		click: defer,
		params: [
			'parcela-celular', parseInt(dv.current()['parcela-celular'] || 0) - 1,
			dv.current()?.file.path
		]
	}
})

dv.header(3, `Valor parcela: R$${parseFloat(dv.current()?.celular || 0)}`);
dv.header(3, `Parcelas faltantes: x${parseFloat(dv.current()['parcela-celular'] || 0)}`);

dv.header(2, `Material Alcié: R$${parseFloat(dv.current()['parcela-material-alcie'] || 0) * parseFloat(dv.current()['material-alcie'] || 0)}`);
createButton({
	app,
	el: this.container,
	args: {name: "Pagou parcela"},
	clickOverride: {
		click: defer,
		params: [
			'parcela-material-alcie', parseInt(dv.current()['parcela-material-alcie'] || 0) - 1,
			dv.current()?.file.path
		]
	}
})

dv.header(3, `Valor parcela: R$${parseFloat(dv.current()['material-alcie'] || 0)}`);
dv.header(3, `Parcelas faltantes: x${parseFloat(dv.current()['parcela-material-alcie'] || 0)}`);

dv.header(2, `Sapato Supermoda: R$${parseFloat(dv.current()['parcela-sapato-supermoda'] || 0) * parseFloat(dv.current()['sapato-supermoda'] || 0)}`);
createButton({
	app,
	el: this.container,
	args: {name: "Pagou parcela"},
	clickOverride: {
		click: defer,
		params: [
			'parcela-sapato-supermoda', parseInt(dv.current()['parcela-sapato-supermoda'] || 0) - 1,
			dv.current()?.file.path
		]
	}
})

dv.header(3, `Valor parcela: R$${parseFloat(dv.current()['sapato-supermoda'] || 0)}`);
dv.header(3, `Parcelas faltantes: x${parseFloat(dv.current()['parcela-sapato-supermoda'] || 0)}`);

dv.header(2, `Mochila Supermoda: R$${parseFloat(dv.current()['parcela-mochila-supermoda'] || 0) * parseFloat(dv.current()['mochila-supermoda'] || 0)}`);
createButton({
	app,
	el: this.container,
	args: {name: "Pagou parcela"},
	clickOverride: {
		click: defer,
		params: [
			'parcela-mochila-supermoda', parseInt(dv.current()['parcela-mochila-supermoda'] || 0) - 1,
			dv.current()?.file.path
		]
	}
})

dv.header(3, `Valor parcela: R$${parseFloat(dv.current()['mochila-supermoda'] || 0)}`);
dv.header(3, `Parcelas faltantes: x${parseFloat(dv.current()['parcela-mochila-supermoda'] || 0)}`);
```

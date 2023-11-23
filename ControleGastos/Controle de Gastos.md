
```dataviewjs
const {createButton} = app.plugins.plugins["buttons"];
const {update} = this.app.plugins.plugins["metaedit"].api;
const prompt = app.plugins.plugins['templater-obsidian'].templater.functions_generator.internal_functions.modules_array[5].static_functions.get('prompt');
async function defer(key, value, file){
	await update(key, value > 0 ? value : 0, file);
}
async function atualizarValor(key, value, file){
	if (key == 'vr')
		await atualizarValorVR(key, value, file);
}
async function atualizarValorVR(key, value, file){
	let adicionar = parseFloat(await prompt("Quanto foi gasto no VR"));
	await defer(`gastos-${key}`, value.gasto + adicionar, file.saida);
	await defer(`restante-${key}`, value.restante - adicionar, file.entrada);
}

let entradas = dv.page(`ControleGastos/Entradas.md`);
let saidas = dv.page(`ControleGastos/Saídas.md`);

dv.header(2, `Restante Salário: ${entradas['restante-salario']}`);
dv.header(2, `Restante VR: ${entradas['restante-vr']}`);


createButton({
	app,
	el: this.container,
	args: {name: "Adicionar Gasto VR"},
	clickOverride: {
		click: atualizarValor,
		params: [
			'vr', {gasto: parseFloat(saidas['gastos-vr'] || 0), restante: parseFloat(entradas['restante-vr'] || 0)},
			{saida: saidas?.file.path, entrada: entradas?.file.path}
		]
	}
})
```

---
tags:
  - cursos/modulos
completed: true

---

```dataviewjs
const { update } = this.app.plugins.plugins['metaedit'].api;

(async function updatePercentTasks() {
	const tasksModulos = dv.current().file.tasks;
	const incompletedTasks = tasksModulos.where(t=>!t.completed).length;
	
	if(incompletedTasks == 0)
		await update('completed', true, dv.current().file.path);
	else if(dv.current().completed) await update('completed', false, dv.current().file.path);
})()
```
---
- [x] 01- Operadores de igualdade e de negação (unário)
- [x] 02- Operadores de comparação
- [x] 03- Operadores lógicos
- [x] 04- Desafio: operadores de igualdade e lógicos
- [x] 05- Curto-circuito de operadores lógicos
- [x] 06- Precedência de operadores lógicos
- [x] 07- Estrutura condicional if
- [x] 08- Estruturas condifionais else e else if
- [x] 09- Desafio: calculadora complexa de IMC
- [x] 10- Escopos e inicialização de variáveis
- [x] 11- Estrutura condicional switch
- [x] 12- Cláusula break
- [x] 13- Switch Expressions
- [x] 14- Operador ternário
- [x] 15- Desafio: estrutura switch e operador ternário
- [x] 16- Estrutura de repetição for
- [x] 17- Estrutura de repetição while
- [x] 18- estrutura de repetição do/while
- [x] 19- Cláusulas break e continue
- [x] 20- Desafio: estruturas de repetição
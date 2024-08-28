---
tags:
  - cursos/modulos
completed: false

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
1. [ ] [Comparando números da forma correta3m 37s](https://app.algaworks.com/aulas/4729/comparando-numeros-da-forma-correta)
2. [ ] [Caching de classes wrapper5m 36s](https://app.algaworks.com/aulas/4730/caching-de-classes-wrapper)
3. [ ] [Operações matemáticas com java.lang.Math9m 45s](https://app.algaworks.com/aulas/4731/operacoes-matematicas-com-javalangmath)
4. [ ] [Boas práticas: evite float e double se precisão é importante5m 54s](https://app.algaworks.com/aulas/4732/boas-praticas-evite-float-e-double-se-precisao-e-importante)
5. [ ] [Precisão nos cálculos com BigDecimal12m 19s](https://app.algaworks.com/aulas/4733/precisao-nos-calculos-com-bigdecimal)
6. [ ] [Divisão de BigDecimal e formas de arredondamento8m 25s](https://app.algaworks.com/aulas/4734/divisao-de-bigdecimal-e-formas-de-arredondamento)
7. [ ] [Formatação decimal com DecimalFormat21m 24s](https://app.algaworks.com/aulas/4735/formatacao-decimal-com-decimalformat)
8. [ ] [Localizando a formatação de números com Locale8m 0s](https://app.algaworks.com/aulas/4736/localizando-a-formatacao-de-numeros-com-locale)
9. [ ] [Formatação numérica compacta5m 34s](https://app.algaworks.com/aulas/4737/formatacao-numerica-compacta)
10. [ ] [Transformando String em números com DecimalFormat9m 34s](https://app.algaworks.com/aulas/4738/transformando-string-em-numeros-com-decimalformat)
11. [ ] [Desafio: formatação numérica2m 45s](https://app.algaworks.com/aulas/4739/desafio-formatacao-numerica)
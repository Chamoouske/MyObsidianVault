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
1. [ ] [Entendendo os fusos horários8m 55s](https://app.algaworks.com/aulas/4740/entendendo-os-fusos-horarios)
2. [ ] [Instanciando datas com o tipo Date13m 19s](https://app.algaworks.com/aulas/4741/instanciando-datas-com-o-tipo-date)
3. [ ] [Calculando e comparando datas com Date6m 42s](https://app.algaworks.com/aulas/4742/calculando-e-comparando-datas-com-date)
4. [ ] [Formatando Date para String11m 24s](https://app.algaworks.com/aulas/4743/formatando-date-para-string)
5. [ ] [Convertendo de String para Date4m 35s](https://app.algaworks.com/aulas/4744/convertendo-de-string-para-date)
6. [ ] [Conhecendo o tipo Calendar7m 2s](https://app.algaworks.com/aulas/4745/conhecendo-o-tipo-calendar)
7. [ ] [Obtendo unidades de tempo e atribuindo uma Date em Calendar10m 5s](https://app.algaworks.com/aulas/4746/obtendo-unidades-de-tempo-e-atribuindo-uma-date-em-calendar)
8. [ ] [Operações de datas com o tipo Calendar6m 2s](https://app.algaworks.com/aulas/4747/operacoes-de-datas-com-o-tipo-calendar)
9. [ ] [Comparando datas com o tipo Calendar2m 46s](https://app.algaworks.com/aulas/4748/comparando-datas-com-o-tipo-calendar)
10. [ ] [Desafio: calculando datas com Calendar3m 36s](https://app.algaworks.com/aulas/4749/desafio-calculando-datas-com-calendar)
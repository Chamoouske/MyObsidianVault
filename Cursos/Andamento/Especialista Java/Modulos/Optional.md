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
1. [ ] [O jeito tradicional de evitar NPE18m 57s](https://app.algaworks.com/aulas/4809/o-jeito-tradicional-de-evitar-npe)
2. [ ] [Evoluindo seu código com Optional12m 0s](https://app.algaworks.com/aulas/4810/evoluindo-seu-codigo-com-optional)
3. [ ] [Testando valor do Optional com isPresent4m 23s](https://app.algaworks.com/aulas/4811/testando-valor-do-optional-com-ispresent)
4. [ ] [Obtendo valor e lançando exceção com orElseThrow7m 22s](https://app.algaworks.com/aulas/4812/obtendo-valor-e-lancando-excecao-com-orelsethrow)
5. [ ] [Obtendo valor alternativo com orElse e orElseGet6m 55s](https://app.algaworks.com/aulas/4813/obtendo-valor-alternativo-com-orelse-e-orelseget)
6. [ ] [Obtendo e testando valor com ifPresent e ifPresentOrElse6m 0s](https://app.algaworks.com/aulas/4814/obtendo-e-testando-valor-com-ifpresent-e-ifpresentorelse)
7. [ ] [Testando e filtrando valor com Predicate5m 9s](https://app.algaworks.com/aulas/4815/testando-e-filtrando-valor-com-predicate)
8. [ ] [Aplicando transformações com map6m 13s](https://app.algaworks.com/aulas/4816/aplicando-transformacoes-com-map)
9. [ ] [Aplicando transformações com flatMap7m 26s](https://app.algaworks.com/aulas/4817/aplicando-transformacoes-com-flatmap)
10. [ ] [Tipos especiais de Optional para tipos primitivos6m 27s](https://app.algaworks.com/aulas/4818/tipos-especiais-de-optional-para-tipos-primitivos)
11. [ ] [Boas práticas ao usar Optional5m 13s](https://app.algaworks.com/aulas/4819/boas-praticas-ao-usar-optional)
12. [ ] [Desafio: Optional6m 13s](https://app.algaworks.com/aulas/4820/desafio-optional)
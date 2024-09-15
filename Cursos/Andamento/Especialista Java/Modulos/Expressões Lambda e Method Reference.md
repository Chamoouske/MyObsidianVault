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
1. [x] [Introdução ao módulo8m 15s](https://app.algaworks.com/aulas/4792/introducao-ao-modulo)
2. [x] [Implementando Expressões Lambda9m 57s](https://app.algaworks.com/aulas/4793/implementando-expressoes-lambda)
3. [x] [Entendendo as interfaces funcionais3m 22s](https://app.algaworks.com/aulas/4794/entendendo-as-interfaces-funcionais)
4. [x] [Usando a interface @FunctionalInterface4m 59s](https://app.algaworks.com/aulas/4795/usando-a-interface-functionalinterface)
5. [x] [Boas práticas: prefira lambdas a classes anônimas10m 7s](https://app.algaworks.com/aulas/4796/boas-praticas-prefira-lambdas-a-classes-anonimas)
6. [x] [Boas práticas: torne as lambdas mais concisas8m 4s](https://app.algaworks.com/aulas/4797/boas-praticas-torne-as-lambdas-mais-concisas)
7. [x] [Implementando Comparator com lambda6m 46s](https://app.algaworks.com/aulas/4798/implementando-comparator-com-lambda)
8. [x] [Boas práticas: prefira interfaces funcionais padrão7m 44s](https://app.algaworks.com/aulas/4799/boas-praticas-prefira-interfaces-funcionais-padrao)
9. [x] [As 4 principais interfaces funcionais16m 0s](https://app.algaworks.com/aulas/4800/as-4-principais-interfaces-funcionais)
10. [x] [Interface funcional Predicate: removendo elementos de coleções15m 20s](https://app.algaworks.com/aulas/4801/interface-funcional-predicate-removendo-elementos-de-colecoes)
11. [x] [Interface funcional Consumer: iterando em coleções com forEach7m 59s](https://app.algaworks.com/aulas/4802/interface-funcional-consumer-iterando-em-colecoes-com-foreach)
12. [x] [Interface funcional Function: ordenando lista com Comparator.comparing16m 30s](https://app.algaworks.com/aulas/4803/interface-funcional-function-ordenando-lista-com-comparatorcomparing)
13. [x] [Usando Method References6m 55s](https://app.algaworks.com/aulas/4804/usando-method-references)
14. [x] [Referenciando métodos de uma instância particular6m 28s](https://app.algaworks.com/aulas/4805/referenciando-metodos-de-uma-instancia-particular)
15. [x] [Referenciando métodos estáticos2m 22s](https://app.algaworks.com/aulas/4806/referenciando-metodos-estaticos)
16. [x] [Referenciando construtores3m 29s](https://app.algaworks.com/aulas/4807/referenciando-construtores)
17. [x] [Desafio: expressões lambda e method reference3m 43s](https://app.algaworks.com/aulas/4808/desafio-expressoes-lambda-e-method-reference)
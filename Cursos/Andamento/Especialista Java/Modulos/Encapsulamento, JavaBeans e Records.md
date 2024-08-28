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
1. [ ] [O problema da falta de encapsulamento22m 9s](https://app.algaworks.com/aulas/4504/o-problema-da-falta-de-encapsulamento)
2. [ ] [Implementando encapsulamento17m 59s](https://app.algaworks.com/aulas/4505/implementando-encapsulamento)
3. [ ] [JavaBeans e métodos getters e setters13m 38s](https://app.algaworks.com/aulas/4506/javabeans-e-metodos-getters-e-setters)
4. [ ] [IntelliJ IDEA: gerando getters e setters3m 51s](https://app.algaworks.com/aulas/4507/intellij-idea-gerando-getters-e-setters)
5. [ ] [Desafio: encapsulamento e JavaBeans6m 44s](https://app.algaworks.com/aulas/4508/desafio-encapsulamento-e-javabeans)
6. [ ] [Boas práticas: use métodos de acesso em classes públicas (incluindo Tell Don't Ask)14m 6s](https://app.algaworks.com/aulas/4509/boas-praticas-use-metodos-de-acesso-em-classes-publicas-incluindo-tell-dont-ask)
7. [ ] [Código limpo: Lei de Demeter (incluindo Train Wreck)21m 33s](https://app.algaworks.com/aulas/4510/codigo-limpo-lei-de-demeter-incluindo-train-wreck)
8. [ ] [Boas práticas: não permita instanciação com construtor privado3m 0s](https://app.algaworks.com/aulas/4511/boas-praticas-nao-permita-instanciacao-com-construtor-privado)
9. [ ] [Boas práticas: crie cópias defensivas15m 35s](https://app.algaworks.com/aulas/4512/boas-praticas-crie-copias-defensivas)
10. [ ] [Boas práticas: minimize a mutabilidade (incluindo Value Object)25m 38s](https://app.algaworks.com/aulas/4513/boas-praticas-minimize-a-mutabilidade-incluindo-value-object)
11. [ ] [Records15m 14s](https://app.algaworks.com/aulas/4514/records)
12. [ ] [Diagrama de classes: Records3m 23s](https://app.algaworks.com/aulas/4515/diagrama-de-classes-records)
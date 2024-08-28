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
1. [ ] [Conhecendo o projeto deste módulo7m 22s](https://app.algaworks.com/aulas/4516/conhecendo-o-projeto-deste-modulo)
2. [ ] [Criando classes etiquetadas (tagged classes)27m 44s](https://app.algaworks.com/aulas/4517/criando-classes-etiquetadas-tagged-classes)
3. [ ] [Duplicando classes e isolando os comportamentos12m 25s](https://app.algaworks.com/aulas/4518/duplicando-classes-e-isolando-os-comportamentos)
4. [ ] [Conhecendo herança e o relacionamento no diagrama de classes15m 34s](https://app.algaworks.com/aulas/4519/conhecendo-heranca-e-o-relacionamento-no-diagrama-de-classes)
5. [ ] [Implementando herança18m 24s](https://app.algaworks.com/aulas/4520/implementando-heranca)
6. [ ] [Sobrescrita de métodos11m 38s](https://app.algaworks.com/aulas/4521/sobrescrita-de-metodos)
7. [ ] [Modificador de acesso protected17m 39s](https://app.algaworks.com/aulas/4522/modificador-de-acesso-protected)
8. [ ] [Anotação @Override5m 41s](https://app.algaworks.com/aulas/4523/anotacao-override)
9. [ ] [Chamando método da superclasse com super6m 8s](https://app.algaworks.com/aulas/4524/chamando-metodo-da-superclasse-com-super)
10. [ ] [A classe Object5m 9s](https://app.algaworks.com/aulas/4525/a-classe-object)
11. [ ] [Invocando construtores da superclasse11m 48s](https://app.algaworks.com/aulas/4526/invocando-construtores-da-superclasse)
12. [ ] [Criando construtores com parâmetros na superclasse e subclasses8m 30s](https://app.algaworks.com/aulas/4527/criando-construtores-com-parametros-na-superclasse-e-subclasses)
13. [ ] [Boas práticas: sempre sobrescreva o método Object.toString19m 46s](https://app.algaworks.com/aulas/4528/boas-praticas-sempre-sobrescreva-o-metodo-objecttostring)
14. [ ] [Modificador final em classes e métodos14m 9s](https://app.algaworks.com/aulas/4529/modificador-final-em-classes-e-metodos)
15. [ ] [Desafio: implementando herança10m 1s](https://app.algaworks.com/aulas/4530/desafio-implementando-heranca)
16. [ ] [Sobrescrevendo o método Object.equals12m 43s](https://app.algaworks.com/aulas/4531/sobrescrevendo-o-metodo-objectequals)
17. [ ] [Boas práticas: obedeça o contrato ao sobrescrever o método equals7m 24s](https://app.algaworks.com/aulas/4532/boas-praticas-obedeca-o-contrato-ao-sobrescrever-o-metodo-equals)
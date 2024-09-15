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
1. [x] [Conhecendo o projeto deste módulo7m 22s](https://app.algaworks.com/aulas/4516/conhecendo-o-projeto-deste-modulo)
2. [x] [Criando classes etiquetadas (tagged classes)27m 44s](https://app.algaworks.com/aulas/4517/criando-classes-etiquetadas-tagged-classes)
3. [x] [Duplicando classes e isolando os comportamentos12m 25s](https://app.algaworks.com/aulas/4518/duplicando-classes-e-isolando-os-comportamentos)
4. [x] [Conhecendo herança e o relacionamento no diagrama de classes15m 34s](https://app.algaworks.com/aulas/4519/conhecendo-heranca-e-o-relacionamento-no-diagrama-de-classes)
5. [x] [Implementando herança18m 24s](https://app.algaworks.com/aulas/4520/implementando-heranca)
6. [x] [Sobrescrita de métodos11m 38s](https://app.algaworks.com/aulas/4521/sobrescrita-de-metodos)
7. [x] [Modificador de acesso protected17m 39s](https://app.algaworks.com/aulas/4522/modificador-de-acesso-protected)
8. [x] [Anotação @Override5m 41s](https://app.algaworks.com/aulas/4523/anotacao-override)
9. [x] [Chamando método da superclasse com super6m 8s](https://app.algaworks.com/aulas/4524/chamando-metodo-da-superclasse-com-super)
10. [x] [A classe Object5m 9s](https://app.algaworks.com/aulas/4525/a-classe-object)
11. [x] [Invocando construtores da superclasse11m 48s](https://app.algaworks.com/aulas/4526/invocando-construtores-da-superclasse)
12. [x] [Criando construtores com parâmetros na superclasse e subclasses8m 30s](https://app.algaworks.com/aulas/4527/criando-construtores-com-parametros-na-superclasse-e-subclasses)
13. [x] [Boas práticas: sempre sobrescreva o método Object.toString19m 46s](https://app.algaworks.com/aulas/4528/boas-praticas-sempre-sobrescreva-o-metodo-objecttostring)
14. [x] [Modificador final em classes e métodos14m 9s](https://app.algaworks.com/aulas/4529/modificador-final-em-classes-e-metodos)
15. [x] [Desafio: implementando herança10m 1s](https://app.algaworks.com/aulas/4530/desafio-implementando-heranca)
16. [x] [Sobrescrevendo o método Object.equals12m 43s](https://app.algaworks.com/aulas/4531/sobrescrevendo-o-metodo-objectequals)
17. [x] [Boas práticas: obedeça o contrato ao sobrescrever o método equals7m 24s](https://app.algaworks.com/aulas/4532/boas-praticas-obedeca-o-contrato-ao-sobrescrever-o-metodo-equals)
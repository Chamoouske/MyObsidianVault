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
1. [ ] [Introdução às exceções9m 19s](https://app.algaworks.com/aulas/4643/introducao-as-excecoes)
2. [ ] [Lançando exceções20m 26s](https://app.algaworks.com/aulas/4644/lancando-excecoes)
3. [ ] [Stack Trace: interpretando e analisando exceções14m 46s](https://app.algaworks.com/aulas/4645/stack-trace-interpretando-e-analisando-excecoes)
4. [ ] [Capturando exceções com try/catch25m 12s](https://app.algaworks.com/aulas/4646/capturando-excecoes-com-trycatch)
5. [ ] [Relançando exceções e printStackTrace10m 44s](https://app.algaworks.com/aulas/4647/relancando-excecoes-e-printstacktrace)
6. [ ] [Capturando exceções com múltiplos blocos catch6m 19s](https://app.algaworks.com/aulas/4648/capturando-excecoes-com-multiplos-blocos-catch)
7. [ ] [Hierarquia das exceções, checked e unchecked exceptions12m 18s](https://app.algaworks.com/aulas/4649/hierarquia-das-excecoes-checked-e-unchecked-exceptions)
8. [ ] [Capturando checked exceptions12m 23s](https://app.algaworks.com/aulas/4650/capturando-checked-exceptions)
9. [ ] [Criando exceções customizadas13m 4s](https://app.algaworks.com/aulas/4651/criando-excecoes-customizadas)
10. [ ] [Variáveis de instância em exceções customizadas7m 40s](https://app.algaworks.com/aulas/4652/variaveis-de-instancia-em-excecoes-customizadas)
11. [ ] [Lançando e propagando checked exceptions13m 15s](https://app.algaworks.com/aulas/4653/lancando-e-propagando-checked-exceptions)
12. [ ] [Capturando exceções menos específicas (upcasting)17m 51s](https://app.algaworks.com/aulas/4654/capturando-excecoes-menos-especificas-upcasting)
13. [ ] [Capturando e lançando nova exceção8m 17s](https://app.algaworks.com/aulas/4655/capturando-e-lancando-nova-excecao)
14. [ ] [Boa prática: embrulhe a causa raiz5m 36s](https://app.algaworks.com/aulas/4656/boa-pratica-embrulhe-a-causa-raiz)
15. [ ] [Capturando exceções com multi-catch4m 14s](https://app.algaworks.com/aulas/4657/capturando-excecoes-com-multi-catch)
16. [ ] [Usando a cláusula finally12m 50s](https://app.algaworks.com/aulas/4658/usando-a-clausula-finally)
17. [ ] [IntelliJ IDEA: lançando exceções na ferramenta de debug2m 22s](https://app.algaworks.com/aulas/4659/intellij-idea-lancando-excecoes-na-ferramenta-de-debug)
18. [ ] [IntelliJ IDEA: adicionando Java Exception Breakpoints4m 11s](https://app.algaworks.com/aulas/4660/intellij-idea-adicionando-java-exception-breakpoints)
19. [ ] [Boas práticas: lance exceções ao invés de retornar null6m 33s](https://app.algaworks.com/aulas/4661/boas-praticas-lance-excecoes-ao-inves-de-retornar-null)
20. [ ] [Boas práticas: não engula exceções9m 53s](https://app.algaworks.com/aulas/4662/boas-praticas-nao-engula-excecoes)
21. [ ] [Desafio: exceções4m 5s](https://app.algaworks.com/aulas/4663/desafio-excecoes)
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
1. [x] [Conhecendo o projeto de gerador de CSV5m 30s](https://app.algaworks.com/aulas/4952/conhecendo-o-projeto-de-gerador-de-csv)
2. [ ] [Lendo propriedades dinamicamente com Reflection API10m 12s](https://app.algaworks.com/aulas/4953/lendo-propriedades-dinamicamente-com-reflection-api)
3. [ ] [Invocando a leitura de valores de propriedades14m 9s](https://app.algaworks.com/aulas/4954/invocando-a-leitura-de-valores-de-propriedades)
4. [ ] [Introdução às anotações do Java5m 38s](https://app.algaworks.com/aulas/4955/introducao-as-anotacoes-do-java)
5. [ ] [Criando uma anotação customizada10m 23s](https://app.algaworks.com/aulas/4956/criando-uma-anotacao-customizada)
6. [ ] [Processando anotações com Reflection API6m 10s](https://app.algaworks.com/aulas/4957/processando-anotacoes-com-reflection-api)
7. [ ] [Adicionando e processando atributos na anotação6m 55s](https://app.algaworks.com/aulas/4958/adicionando-e-processando-atributos-na-anotacao)
8. [ ] [Classes seladas19m 9s](https://app.algaworks.com/aulas/4959/classes-seladas)
9. [ ] [Conclusão e próximos passos1m 41s](https://app.algaworks.com/aulas/4960/conclusao-e-proximos-passos)
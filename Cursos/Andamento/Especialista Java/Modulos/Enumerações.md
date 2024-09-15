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
1. [x] [Usando enumerações à moda antiga24m 40s](https://app.algaworks.com/aulas/4706/usando-enumeracoes-a-moda-antiga)
2. [x] [Criando tipos Enum9m 50s](https://app.algaworks.com/aulas/4707/criando-tipos-enum)
3. [x] [Diagrama de classes: enumeração2m 48s](https://app.algaworks.com/aulas/4708/diagrama-de-classes-enumeracao)
4. [x] [Usando os métodos do tipo Enum8m 49s](https://app.algaworks.com/aulas/4709/usando-os-metodos-do-tipo-enum)
5. [x] [Declarando e inicializando propriedades e construtores13m 53s](https://app.algaworks.com/aulas/4710/declarando-e-inicializando-propriedades-e-construtores)
6. [x] [Implementando métodos11m 14s](https://app.algaworks.com/aulas/4711/implementando-metodos)
7. [x] [Implementando métodos abstratos9m 24s](https://app.algaworks.com/aulas/4712/implementando-metodos-abstratos)
8. [x] [Boas práticas: substitua parâmetros booleanos por enums5m 4s](https://app.algaworks.com/aulas/4713/boas-praticas-substitua-parametros-booleanos-por-enums)
9. [x] [Desafio: enumerações1m 13s](https://app.algaworks.com/aulas/4714/desafio-enumeracoes)
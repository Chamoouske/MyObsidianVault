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
1. [x] [Introdução ao design de software3m 45s](https://app.algaworks.com/aulas/4941/introducao-ao-design-de-software)
2. [x] [Criando entidade e camada de serviço18m 36s](https://app.algaworks.com/aulas/4942/criando-entidade-e-camada-de-servico)
3. [x] [Conhecendo o pattern Repository1m 48s](https://app.algaworks.com/aulas/4943/conhecendo-o-pattern-repository)
4. [x] [Implementando uma classe Repository10m 56s](https://app.algaworks.com/aulas/4944/implementando-uma-classe-repository)
5. [x] [Implementando uma consulta no repositório9m 47s](https://app.algaworks.com/aulas/4945/implementando-uma-consulta-no-repositorio)
6. [x] [Desacoplando a conexão com o banco de dados10m 8s](https://app.algaworks.com/aulas/4946/desacoplando-a-conexao-com-o-banco-de-dados)
7. [x] [Implementando uma fábrica de Repository8m 44s](https://app.algaworks.com/aulas/4947/implementando-uma-fabrica-de-repository)
8. [x] [Desacoplando a implementação de Repository6m 57s](https://app.algaworks.com/aulas/4948/desacoplando-a-implementacao-de-repository)
9. [x] [Alternando a implementação do Repository11m 23s](https://app.algaworks.com/aulas/4949/alternando-a-implementacao-do-repository)
10. [x] [Abstraindo a fábrica de repositórios10m 56s](https://app.algaworks.com/aulas/4950/abstraindo-a-fabrica-de-repositorios)
11. [x] [Criando um arquivo de configuração (properties)13m 27s](https://app.algaworks.com/aulas/4951/criando-um-arquivo-de-configuracao-properties)
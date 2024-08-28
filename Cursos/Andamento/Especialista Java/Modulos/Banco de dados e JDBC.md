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
1. [ ] [Introdução ao MySQL2m 20s](https://app.algaworks.com/aulas/4929/introducao-ao-mysql)
2. [ ] [Instalando o MySQL Server1m 46s](https://app.algaworks.com/aulas/4930/instalando-o-mysql-server)
3. [ ] [Instalando o MySQL Workbench7m 52s](https://app.algaworks.com/aulas/4931/instalando-o-mysql-workbench)
4. [ ] [Criando uma tabela no banco de dados5m 0s](https://app.algaworks.com/aulas/4932/criando-uma-tabela-no-banco-de-dados)
5. [ ] [Introdução ao JDBC6m 42s](https://app.algaworks.com/aulas/4933/introducao-ao-jdbc)
6. [ ] [Adicionando driver JDBC ao projeto e criando uma conexão18m 8s](https://app.algaworks.com/aulas/4934/adicionando-driver-jdbc-ao-projeto-e-criando-uma-conexao)
7. [ ] [Executando consultas SQL com Statement17m 2s](https://app.algaworks.com/aulas/4935/executando-consultas-sql-com-statement)
8. [ ] [Realizando consultas SQL com a cláusula where6m 32s](https://app.algaworks.com/aulas/4936/realizando-consultas-sql-com-a-clausula-where)
9. [ ] [Executando consultas SQL com PreparedStatement6m 53s](https://app.algaworks.com/aulas/4937/executando-consultas-sql-com-preparedstatement)
10. [ ] [Executando comandos que alteram dados (DML)8m 30s](https://app.algaworks.com/aulas/4938/executando-comandos-que-alteram-dados-dml)
11. [ ] [Obtendo código de autoincremento gerado4m 21s](https://app.algaworks.com/aulas/4939/obtendo-codigo-de-autoincremento-gerado)
12. [ ] [Gerenciando transações com o banco de dados11m 20s](https://app.algaworks.com/aulas/4940/gerenciando-transacoes-com-o-banco-de-dados)
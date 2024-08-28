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
1. [ ] [O que são os arquivos JAR3m 7s](https://app.algaworks.com/aulas/4897/o-que-sao-os-arquivos-jar)
2. [ ] [Gerando arquivos JAR como bibliotecas8m 14s](https://app.algaworks.com/aulas/4898/gerando-arquivos-jar-como-bibliotecas)
3. [ ] [Importando arquivos JAR no projeto5m 1s](https://app.algaworks.com/aulas/4899/importando-arquivos-jar-no-projeto)
4. [ ] [Usando bibliotecas terceiras8m 26s](https://app.algaworks.com/aulas/4900/usando-bibliotecas-terceiras)
5. [ ] [Gerando arquivos JAR executáveis12m 7s](https://app.algaworks.com/aulas/4901/gerando-arquivos-jar-executaveis)
6. [ ] [O que é Apache Maven?9m 9s](https://app.algaworks.com/aulas/4902/o-que-e-apache-maven)
7. [ ] [Instalando o Apache Maven no Windows6m 49s](https://app.algaworks.com/aulas/4903/instalando-o-apache-maven-no-windows)
8. [ ] [Instalando o Apache Maven no macOS e Linux3m 28s](https://app.algaworks.com/aulas/4904/instalando-o-apache-maven-no-macos-e-linux)
9. [ ] [Criando um projeto Maven com IntelliJ IDEA5m 4s](https://app.algaworks.com/aulas/4905/criando-um-projeto-maven-com-intellij-idea)
10. [ ] [Arquivo pom.xml e Maven Coordinates11m 26s](https://app.algaworks.com/aulas/4906/arquivo-pomxml-e-maven-coordinates)
11. [ ] [Entendendo o Standard Directory Layout4m 23s](https://app.algaworks.com/aulas/4907/entendendo-o-standard-directory-layout)
12. [ ] [Compilando e empacotando com Maven14m 10s](https://app.algaworks.com/aulas/4908/compilando-e-empacotando-com-maven)
13. [ ] [Conhecendo os tipos de repositórios Maven5m 7s](https://app.algaworks.com/aulas/4909/conhecendo-os-tipos-de-repositorios-maven)
14. [ ] [Instalando e adicionando dependências com Maven10m 16s](https://app.algaworks.com/aulas/4910/instalando-e-adicionando-dependencias-com-maven)
15. [ ] [Usando dependência do Maven Central Repository7m 12s](https://app.algaworks.com/aulas/4911/usando-dependencia-do-maven-central-repository)
16. [ ] [Entendendo as dependências transitivas5m 50s](https://app.algaworks.com/aulas/4912/entendendo-as-dependencias-transitivas)
17. [ ] [Entendendo os plugins do Maven e o Super POM8m 30s](https://app.algaworks.com/aulas/4913/entendendo-os-plugins-do-maven-e-o-super-pom)
18. [ ] [Gerando Fat JAR com Maven Assembly Plugin10m 52s](https://app.algaworks.com/aulas/4914/gerando-fat-jar-com-maven-assembly-plugin)
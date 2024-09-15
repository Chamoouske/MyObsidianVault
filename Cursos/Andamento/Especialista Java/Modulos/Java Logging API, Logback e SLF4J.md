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
1. [x] [Por que fazer logging?10m 21s](https://app.algaworks.com/aulas/4915/por-que-fazer-logging)
2. [x] [Principais frameworks de logging6m 44s](https://app.algaworks.com/aulas/4916/principais-frameworks-de-logging)
3. [x] [Usando o Java Logging API (JUL)10m 51s](https://app.algaworks.com/aulas/4917/usando-o-java-logging-api-jul)
4. [x] [Conhecendo os níveis de log do JUL11m 57s](https://app.algaworks.com/aulas/4918/conhecendo-os-niveis-de-log-do-jul)
5. [x] [Registrando um log de exceção com JUL9m 29s](https://app.algaworks.com/aulas/4919/registrando-um-log-de-excecao-com-jul)
6. [x] [Criando logging.properties e configurando nível de log11m 12s](https://app.algaworks.com/aulas/4920/criando-loggingproperties-e-configurando-nivel-de-log)
7. [x] [Salvando logs em arquivos com FileHandler do JUL6m 44s](https://app.algaworks.com/aulas/4921/salvando-logs-em-arquivos-com-filehandler-do-jul)
8. [x] [Usando a Java Logging API com SLF4J16m 43s](https://app.algaworks.com/aulas/4922/usando-a-java-logging-api-com-slf4j)
9. [x] [Usando o Logback com SLF4J6m 25s](https://app.algaworks.com/aulas/4923/usando-o-logback-com-slf4j)
10. [x] [Conhecendo os níveis de log do Logback e SLF4J5m 30s](https://app.algaworks.com/aulas/4924/conhecendo-os-niveis-de-log-do-logback-e-slf4j)
11. [x] [Configurando a saída de logs com logback.xml23m 40s](https://app.algaworks.com/aulas/4925/configurando-a-saida-de-logs-com-logbackxml)
12. [x] [Customizando mais o padrão de layout do Encoder9m 27s](https://app.algaworks.com/aulas/4926/customizando-mais-o-padrao-de-layout-do-encoder)
13. [x] [Salvando logs em arquivos com FileAppender do Logback4m 36s](https://app.algaworks.com/aulas/4927/salvando-logs-em-arquivos-com-fileappender-do-logback)
14. [x] [Desafio: Logback e SLF4J3m 35s](https://app.algaworks.com/aulas/4928/desafio-logback-e-slf4j)
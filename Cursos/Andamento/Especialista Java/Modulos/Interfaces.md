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
1. [x] [Entendendo as interfaces13m 50s](https://app.algaworks.com/aulas/4544/entendendo-as-interfaces)
2. [x] [Criando a primeira interface25m 0s](https://app.algaworks.com/aulas/4545/criando-a-primeira-interface)
3. [x] [Implementando a primeira interface18m 58s](https://app.algaworks.com/aulas/4546/implementando-a-primeira-interface)
4. [x] [Nova interface e injeção de dependências18m 18s](https://app.algaworks.com/aulas/4547/nova-interface-e-injecao-de-dependencias)
5. [x] [Conhecendo o projeto da financeira14m 38s](https://app.algaworks.com/aulas/4548/conhecendo-o-projeto-da-financeira)
6. [x] [Quando herança de classes se torna um problema24m 1s](https://app.algaworks.com/aulas/4549/quando-heranca-de-classes-se-torna-um-problema)
7. [x] [Código mais flexível: refatorando para usar interfaces14m 39s](https://app.algaworks.com/aulas/4550/codigo-mais-flexivel-refatorando-para-usar-interfaces)
8. [x] [Métodos default em interfaces15m 17s](https://app.algaworks.com/aulas/4551/metodos-default-em-interfaces)
9. [x] [Classes abstratas com interfaces14m 3s](https://app.algaworks.com/aulas/4552/classes-abstratas-com-interfaces)
10. [x] [Métodos privados em interfaces4m 33s](https://app.algaworks.com/aulas/4553/metodos-privados-em-interfaces)
11. [x] [Métodos estáticos em interfaces2m 40s](https://app.algaworks.com/aulas/4554/metodos-estaticos-em-interfaces)
12. [x] [Variáveis são estáticas e finais em interfaces4m 49s](https://app.algaworks.com/aulas/4555/variaveis-sao-estaticas-e-finais-em-interfaces)
13. [x] [Implementando múltiplas interfaces16m 25s](https://app.algaworks.com/aulas/4556/implementando-multiplas-interfaces)
14. [x] [Herança de interfaces5m 28s](https://app.algaworks.com/aulas/4557/heranca-de-interfaces)
15. [x] [Desafio: interfaces13m 57s](https://app.algaworks.com/aulas/4558/desafio-interfaces)
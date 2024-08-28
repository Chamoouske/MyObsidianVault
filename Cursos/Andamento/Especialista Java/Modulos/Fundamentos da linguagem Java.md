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
- [x] 01- Criando o primeiro programa Java
- [x] 02- Compilando e executando um programa Java
- [x] 03- Desafio: correção de erros
- [x] 04- Escrevendo comentários no código
- [ ] 05- Conhecendo e usando convenções de código
- [ ] 06- Palavras reservadas
- [ ] 07- Trabalhando com variáveis
- [ ] 08- Operadores aritméticos
- [ ] 09- Desafio: variáveis e operadores aritméticos
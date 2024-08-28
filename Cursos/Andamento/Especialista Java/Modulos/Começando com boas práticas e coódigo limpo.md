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
- [x] 01- Boas práticas com Effective Java e Clean Code
- [x] 02- Código Limpo: escolha bons nomes
- [x] 03- Código Limpo: tamanho e organização de classes
- [x] 04- Código Limpo: comentários no código
- [x] 05- Código Limpo: métodos pequenos e que fazem só uma coisa
- [x] 06- Código Limpo: pensando melhor nos argumentos de métodos
- [x] 07- Boas práticas: valide os argumentos
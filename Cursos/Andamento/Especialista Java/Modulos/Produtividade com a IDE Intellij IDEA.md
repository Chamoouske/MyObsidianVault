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
- [x] 01- Conhecendo as IDEs mais populares
- [x] 02- Instalando e conhecendo a IntelliJ IDEA
- [x] 03- Mais da IntelliJ IDEA: build, run, plugins, terminal e shared index
- [x] 04- Usando o Code Completion, Live Templates e Postfix Completion
- [x] 05- Conhecendo os principais atalhos
- [x] 06- Mais atalhos do IntelliJ IDEA
- [x] 07- Usando o Debugger para depurar seu código
- [x] 08- Debugger: silenciamento, condiçãoe desativação de breakpoints
- [x] 09- Debugger: gerenciando variáveis e avaliando expressões
- [x] 10- Debugger: watches e logging
- [x] 11- Rascunhando e testando o código com Scratch Files
- [x] 12- Testando código com JShell Console da IDE
- [x] 13- Consistência no estilo de codificação com EditorConfig
- [x] 14- Importando um projeto existente na IDE
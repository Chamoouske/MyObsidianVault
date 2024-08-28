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
- [x] 01- Introdução ao curso
- [x] 02- Como aprender Java e pedir ajuda
- [x] 03- Por que aprender Java?
- [x] 04- Um pouco sobre a história do Java
- [x] 05- Conhecendo as plataformas Java
- [x] 06- Conhecendo a Máquina Virtual Java (JVM)
- [x] 07- JRE e JDK: qual a diferença?
- [x] 08- Conhecendo as versões do Java
- [x] 09- Conhecendo as distribuições JDKs e licenças de uso
- [x] 10- Instalando o JDK no Ubuntu e macOS com SDKMan!
- [x] 11- Instalando o JDK no Windows
- [x] 12- Escolhendo um editor de código simples
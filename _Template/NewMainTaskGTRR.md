<%*
let title = tp.file.title;
if(title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await prompt("Título da tarefa")
	await tp.file.rename(title.replace(/[^*\\/"<>:|?]+/, ''))
}

const prompt = tp.system.prompt;
const suggester = tp.system.suggester;
const {update} = this.app.plugins.plugins["metaedit"].api;
const dv = this.app.plugins.plugins['dataview'].api;
const tasks = await dv.pages(`"${tp.file.path(true).split('.')[0]}"`).file.tasks;

function parseDateWithNLDates(date){
	return app.plugins.plugins['nldates-obsidian'].parseDate(date).moment.format("YYYY-MM-DD")
}

let status = await suggester(
	["To Do", "In Progress", "Completed"],
	["To Do", "In Progress", "Completed"],
	false,
	"Status"
) || "To Do";

let priority = await suggester(
	["Low", "Midium", "High", "Imediate"],
	["Low", "Midium", "High", "Imediate"],
	false,
	"Prioridade"
) || "Low";

let until = parseDateWithNLDates(await prompt("Until") || "today");

let project = await suggester(
	["Personal", "GTRR", "Other"],
	["Personal", "GTRR", "Other"],
	false,
	"Projeto"
) || "Personal";

await tp.file.move("Tasks/" + title.replace(/[^*\\/"<>:|?]+/, ''))
%>---

status: <% status %>
priority: <% priority %>
until: <% until %>
project: <% project %>

Total: <% await tasks.length %>
Complete: <% await tasks.where(t=>t.completed).length %>
Incomplete: <% await tasks.where(t=>!t.completed).length %>

---
```dataviewjs
const {update} = this.app.plugins.plugins['metaedit'].api;

(async () => {
	const tasks = dv.current().file.tasks;
	const completedTasks = tasks.where(t=>t.completed).length;
	const incompletedTasks = tasks.where(t=>!t.completed).length;
	
	await update('Total', tasks.length, dv.current().file.path)
	await update('Complete', completedTasks, dv.current().file.path)
	await update('Incomplete', incompletedTasks, dv.current().file.path)
})()
```
## Description


## Tasks

- [ ]  <% tp.file.cursor() %>
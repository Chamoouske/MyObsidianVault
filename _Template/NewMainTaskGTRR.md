<%*
const prompt = tp.system.prompt;
const suggester = tp.system.suggester;
const {update} = this.app.plugins.plugins["metaedit"].api;
const dv = this.app.plugins.plugins['dataview'].api;
const tasks = dv.pages(`"${tp.file.path(true)}"`).file.tasks;

function parseDateWithNLDates(date){
	return app.plugins.plugins['nldates-obsidian'].parseDate(date).moment.format("YYYY-MM-DD")
}

let title = tp.file.title;
if(title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await prompt("Título da tarefa")
	await tp.file.rename(title)
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
_%>---
Status: <% status %>
Priority: <% priority %>
Until: <% until %>

Total: <% tasks.length %>
Complete: <% tasks.where(t=>t.completed).length %>
Incomplete: <% tasks.where(t=>!t.completed).length %>
---
```dataview
TASK
FROM "GTRR/Tasks"
WHERE !completed
```

- [ ]  <% tp.file.cursor() %>
- [x] Teste
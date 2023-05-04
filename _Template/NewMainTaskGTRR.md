<%*
const prompt = tp.system.prompt;
const suggester = tp.system.suggester;
const {autoprop} = this.app.plugins.plugins["metaedit"].api;

let t;
function parseDateWithNLDates(date){
	t = date
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

Total: 1
Complete: 0
Incomplete: 1
---
```dataview
TABLE
	Priority,
	Until
FROM "GTRR/Tasks"
```

- [ ]  <% t %> <% tp.file.cursor() %>
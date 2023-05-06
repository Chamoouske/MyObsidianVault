<%*
const prompt = tp.system.prompt;
const suggester = tp.system.suggester;
const {update} = this.app.plugins.plugins["metaedit"].api;
const dv = this.app.plugins.plugins['dataview'].api;
const tasks = await dv.pages(`"${tp.file.path(true).split('.')[0]}"`).file.tasks;

let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if(title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await prompt("Título da tarefa");
}

function parseDateWithNLDates(date){
	if(!date) return ''
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

let until = parseDateWithNLDates(await prompt("Until") || "");

let project = await suggester(
	["Personal", "GTRR", "Other"],
	["Personal", "GTRR", "Other"],
	false,
	"Projeto"
) || "Personal";

await tp.file.move(`Tasks/${project}/${title.replace(re, '_')}`);
%>---

status: <% status %>
priority: <% priority %>
until: <% until %>
project: <% project %>

Total: <% await tasks.length %>
Complete: <% await tasks.where(t=>t.completed).length %>
Incomplete: <% await tasks.where(t=>!t.completed).length %>

---
## Description


## Tasks
- [ ]  <% tp.file.cursor() %>
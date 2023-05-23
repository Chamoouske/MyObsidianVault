<%*
const prompt = tp.system.prompt;
const suggester = tp.system.suggester;

let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if(title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await prompt("Título da tarefa");
}

let status = await suggester(
	["To Do", "In Progress", "Completed"],
	["To Do", "In Progress", "Completed"],
	false,
	"Status"
) || "To Do";

await tp.file.create_new(tp.file.find_tfile('Requisito'), title.replace(re, '_'));
await tp.file.move(`Projetos/${title.replace(re, '_')}/${title.replace(re, '_')}`);
%>---
Status: <% status %>
Added: <% tp.file.creation_date("YYYY-MM-DD") %>
---


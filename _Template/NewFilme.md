<%*
let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await tp.system.prompt("Nome do filme: ");
	await tp.file.move('Filmes/' + title.replace(re, '_'))
}

const indicou = await tp.system.suggester(
	["Eu", "Conje"],
	["Eu", "Conje"],
	false,
	"Quem indicou:"
)
%>---
Titulo: <% title %>
Indicado-por: <% indicou %>
Assistido: false
---
## Descrição

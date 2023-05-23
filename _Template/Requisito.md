<%*
const prompt = tp.system.prompt;
const suggester = tp.system.suggester;

let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if(title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = await prompt("Título da tarefa");
}

await tp.file.move(`Projetos/${title.replace(re, '_')}/Requisitos/${title.replace(re, '_')}`);
%>---
---
## Requisitos Funcionais
- [ ] 

## Requisitos Não Funcionais
- [ ] 

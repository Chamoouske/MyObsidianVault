<%*
const { update } = this.app.plugins.plugins['metaedit'].api;

let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.contains("Untitled") || title.contains("Sem título")){
	title = (await tp.system.prompt("Título do Módulo: ")).replace(re, '_');
}

await tp.file.rename(title);
%>
- [ ] Aula 1

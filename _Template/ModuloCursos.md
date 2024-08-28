<%*
const { update } = this.app.plugins.plugins['metaedit'].api;

let title = tp.file.title;
const re = /[*:"\\|<>/?]/g;
if (title.startsWith("Untitled") || title.startsWith("Sem título")){
	title = (await tp.system.prompt("Nome do Anime: ")).replace(re, '_');
}
const pathCurso = `Cursos/Andamento/${title}`;
await tp.file.move(`${pathCurso}/${title}`);
%>
- [ ] Aula 1

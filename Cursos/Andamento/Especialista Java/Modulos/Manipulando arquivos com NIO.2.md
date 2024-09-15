---
tags:
  - cursos/modulos
completed: false

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
1. [x] [Introdução ao NIO e NIO.23m 36s](https://app.algaworks.com/aulas/4868/introducao-ao-nio-e-nio2)
2. [x] [Representando arquivos e pastas com a classe Path14m 59s](https://app.algaworks.com/aulas/4869/representando-arquivos-e-pastas-com-a-classe-path)
3. [x] [Trabalhando com caminhos absolutos e relativos8m 38s](https://app.algaworks.com/aulas/4870/trabalhando-com-caminhos-absolutos-e-relativos)
4. [x] [Operações básicas com a classe Files6m 40s](https://app.algaworks.com/aulas/4871/operacoes-basicas-com-a-classe-files)
5. [x] [Copiando arquivos e diretórios7m 42s](https://app.algaworks.com/aulas/4872/copiando-arquivos-e-diretorios)
6. [ ] [Movendo arquivos e diretórios3m 39s](https://app.algaworks.com/aulas/4873/movendo-arquivos-e-diretorios)
7. [ ] [Excluindo arquivos e diretórios4m 49s](https://app.algaworks.com/aulas/4874/excluindo-arquivos-e-diretorios)
8. [ ] [Realizando operações com Files.walkFileTree14m 17s](https://app.algaworks.com/aulas/4875/realizando-operacoes-com-fileswalkfiletree)
9. [ ] [Obtendo informações de arquivos e diretórios6m 21s](https://app.algaworks.com/aulas/4876/obtendo-informacoes-de-arquivos-e-diretorios)
10. [ ] [Listando conteúdo de diretórios7m 58s](https://app.algaworks.com/aulas/4877/listando-conteudo-de-diretorios)
11. [ ] [Pesquisando arquivos em uma pasta e subpastas7m 29s](https://app.algaworks.com/aulas/4878/pesquisando-arquivos-em-uma-pasta-e-subpastas)
12. [ ] [Entendendo os buffers e usando ByteBuffer12m 22s](https://app.algaworks.com/aulas/4879/entendendo-os-buffers-e-usando-bytebuffer)
13. [ ] [Usando CharBuffer7m 42s](https://app.algaworks.com/aulas/4880/usando-charbuffer)
14. [ ] [Decodificando ByteBuffer em CharBuffer10m 51s](https://app.algaworks.com/aulas/4881/decodificando-bytebuffer-em-charbuffer)
15. [ ] [Lendo arquivos com ByteChannel9m 10s](https://app.algaworks.com/aulas/4882/lendo-arquivos-com-bytechannel)
16. [ ] [Lendo arquivos com buffers menores10m 50s](https://app.algaworks.com/aulas/4883/lendo-arquivos-com-buffers-menores)
17. [ ] [Escrevendo arquivos com ByteChannel8m 30s](https://app.algaworks.com/aulas/4884/escrevendo-arquivos-com-bytechannel)
18. [ ] [Usando a API de I/O clássica com implementações da NIO8m 12s](https://app.algaworks.com/aulas/4885/usando-a-api-de-io-classica-com-implementacoes-da-nio)
19. [ ] [Simplificando a leitura de arquivos com a classe Files6m 13s](https://app.algaworks.com/aulas/4886/simplificando-a-leitura-de-arquivos-com-a-classe-files)
20. [ ] [Simplificando a escrita de arquivos com a classe Files3m 25s](https://app.algaworks.com/aulas/4887/simplificando-a-escrita-de-arquivos-com-a-classe-files)
21. [ ] [Desafio: NIO.22m 31s](https://app.algaworks.com/aulas/4888/desafio-nio2)
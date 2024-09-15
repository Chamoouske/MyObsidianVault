---
tags:
  - cursos/modulos
completed: true
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
1. [x] [Introdução à API clássica de I/O2m 5s](https://app.algaworks.com/aulas/4850/introducao-a-api-classica-de-io)
2. [x] [Instanciando e criando arquivos e pastas com a classe File12m 38s](https://app.algaworks.com/aulas/4851/instanciando-e-criando-arquivos-e-pastas-com-a-classe-file)
3. [x] [Obtendo o caminho absoluto e canônico de File7m 41s](https://app.algaworks.com/aulas/4852/obtendo-o-caminho-absoluto-e-canonico-de-file)
4. [x] [Excluindo, renomeando e movendo arquivos e pastas8m 5s](https://app.algaworks.com/aulas/4853/excluindo-renomeando-e-movendo-arquivos-e-pastas)
5. [x] [Obtendo informações de arquivos e diretórios7m 41s](https://app.algaworks.com/aulas/4854/obtendo-informacoes-de-arquivos-e-diretorios)
6. [x] [Listando arquivos e diretórios6m 45s](https://app.algaworks.com/aulas/4855/listando-arquivos-e-diretorios)
7. [x] [Entendendo I/O streams e Byte-oriented streams4m 49s](https://app.algaworks.com/aulas/4856/entendendo-io-streams-e-byte-oriented-streams)
8. [x] [Lendo arquivos com FileInputStream14m 9s](https://app.algaworks.com/aulas/4857/lendo-arquivos-com-fileinputstream)
9. [x] [Boa prática: tratando IOException com try-with-resources5m 12s](https://app.algaworks.com/aulas/4858/boa-pratica-tratando-ioexception-com-try-with-resources)
10. [x] [Escrevendo arquivos com FileOutputStream6m 28s](https://app.algaworks.com/aulas/4859/escrevendo-arquivos-com-fileoutputstream)
11. [x] [Conhecendo Character-oriented streams4m 4s](https://app.algaworks.com/aulas/4860/conhecendo-character-oriented-streams)
12. [x] [Lendo arquivos de texto com FileReader8m 43s](https://app.algaworks.com/aulas/4861/lendo-arquivos-de-texto-com-filereader)
13. [x] [Escrevendo arquivos de texto com FileWriter2m 56s](https://app.algaworks.com/aulas/4862/escrevendo-arquivos-de-texto-com-filewriter)
14. [x] [Lendo arquivos texto de forma otimizada com BufferedReader5m 53s](https://app.algaworks.com/aulas/4863/lendo-arquivos-texto-de-forma-otimizada-com-bufferedreader)
15. [x] [Escrevendo arquivos texto de forma otimizada com BufferedWriter4m 4s](https://app.algaworks.com/aulas/4864/escrevendo-arquivos-texto-de-forma-otimizada-com-bufferedwriter)
16. [x] [Reconhecendo a API de I/O em System.in e Scanner8m 44s](https://app.algaworks.com/aulas/4865/reconhecendo-a-api-de-io-em-systemin-e-scanner)
17. [x] [Reconhecendo a API de I/O em System.out e a classe PrintStream7m 44s](https://app.algaworks.com/aulas/4866/reconhecendo-a-api-de-io-em-systemout-e-a-classe-printstream)
18. [x] [Desafio: API clássica de I/O5m 55s](https://app.algaworks.com/aulas/4867/desafio-api-classica-de-io)
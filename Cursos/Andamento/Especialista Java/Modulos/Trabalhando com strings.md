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
1. [x] [Comparação de strings5m 1s](https://app.algaworks.com/aulas/4715/comparacao-de-strings)
2. [x] [Pool de strings2m 52s](https://app.algaworks.com/aulas/4716/pool-de-strings)
3. [x] [Validando o conteúdo de strings7m 53s](https://app.algaworks.com/aulas/4717/validando-o-conteudo-de-strings)
4. [x] [Extraindo trechos da String com indexOf e substring14m 20s](https://app.algaworks.com/aulas/4718/extraindo-trechos-da-string-com-indexof-e-substring)
5. [x] [Extraindo trechos da String com lastIndexOf e substring3m 36s](https://app.algaworks.com/aulas/4719/extraindo-trechos-da-string-com-lastindexof-e-substring)
6. [x] [Transformando strings11m 6s](https://app.algaworks.com/aulas/4720/transformando-strings)
7. [x] [Implementando algoritmos usando os métodos da classe String11m 55s](https://app.algaworks.com/aulas/4721/implementando-algoritmos-usando-os-metodos-da-classe-string)
8. [x] [Desafio: validação de e-mail8m 42s](https://app.algaworks.com/aulas/4722/desafio-validacao-de-e-mail)
9. [x] [Testando correspondências de strings com expressões regulares23m 36s](https://app.algaworks.com/aulas/4723/testando-correspondencias-de-strings-com-expressoes-regulares)
10. [x] [Web Scraping: buscando correspondências com Pattern e Matcher19m 24s](https://app.algaworks.com/aulas/4724/web-scraping-buscando-correspondencias-com-pattern-e-matcher)
11. [x] [Manipulando strings com expressões regulares6m 42s](https://app.algaworks.com/aulas/4725/manipulando-strings-com-expressoes-regulares)
12. [x] [Boas práticas: use StringBuilder para mais performance8m 39s](https://app.algaworks.com/aulas/4726/boas-praticas-use-stringbuilder-para-mais-performance)
13. [x] [Código mais limpo com Text blocks7m 48s](https://app.algaworks.com/aulas/4727/codigo-mais-limpo-com-text-blocks)
14. [x] [Desafio: Text blocks e expressões regulares1m 58s](https://app.algaworks.com/aulas/4728/desafio-text-blocks-e-expressoes-regulares)
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
1. [ ] [Por que mais uma API?5m 9s](https://app.algaworks.com/aulas/4671/por-que-mais-uma-api)
2. [ ] [Introdução às listas e ao tipo List5m 3s](https://app.algaworks.com/aulas/4672/introducao-as-listas-e-ao-tipo-list)
3. [ ] [Como funciona a ArrayList15m 20s](https://app.algaworks.com/aulas/4673/como-funciona-a-arraylist)
4. [ ] [Usando listas do tipo ArrayList12m 14s](https://app.algaworks.com/aulas/4674/usando-listas-do-tipo-arraylist)
5. [ ] [Iterando em lista com for tradicional5m 10s](https://app.algaworks.com/aulas/4675/iterando-em-lista-com-for-tradicional)
6. [ ] [Usando listas com Generics10m 24s](https://app.algaworks.com/aulas/4676/usando-listas-com-generics)
7. [ ] [Localizando objetos em listas13m 42s](https://app.algaworks.com/aulas/4677/localizando-objetos-em-listas)
8. [ ] [Manipulando objetos da lista17m 58s](https://app.algaworks.com/aulas/4678/manipulando-objetos-da-lista)
9. [ ] [Percorrendo a lista com Iterator15m 18s](https://app.algaworks.com/aulas/4679/percorrendo-a-lista-com-iterator)
10. [ ] [Percorrendo a lista com ListIterator5m 32s](https://app.algaworks.com/aulas/4680/percorrendo-a-lista-com-listiterator)
11. [ ] [Percorrendo Iterables com enhanced for16m 45s](https://app.algaworks.com/aulas/4681/percorrendo-iterables-com-enhanced-for)
12. [ ] [LinkedList: mais performance na adição e remoção11m 12s](https://app.algaworks.com/aulas/4682/linkedlist-mais-performance-na-adicao-e-remocao)
13. [ ] [Usando listas do tipo LinkedList4m 48s](https://app.algaworks.com/aulas/4683/usando-listas-do-tipo-linkedlist)
14. [ ] [Vector: a lista thread-safe4m 25s](https://app.algaworks.com/aulas/4684/vector-a-lista-thread-safe)
15. [ ] [Boas práticas: reduza o acoplamento usando o tipo da interface6m 21s](https://app.algaworks.com/aulas/4685/boas-praticas-reduza-o-acoplamento-usando-o-tipo-da-interface)
16. [ ] [Convertendo de lista para array5m 16s](https://app.algaworks.com/aulas/4686/convertendo-de-lista-para-array)
17. [ ] [Ordenando listas pela ordem natural5m 22s](https://app.algaworks.com/aulas/4687/ordenando-listas-pela-ordem-natural)
18. [ ] [Boas práticas: considere implementar a interface Comparable14m 39s](https://app.algaworks.com/aulas/4688/boas-praticas-considere-implementar-a-interface-comparable)
19. [ ] [Comparators: ordenando listas com outros critérios12m 28s](https://app.algaworks.com/aulas/4689/comparators-ordenando-listas-com-outros-criterios)
20. [ ] [Desafio: listas3m 46s](https://app.algaworks.com/aulas/4690/desafio-listas)
21. [ ] [Introdução aos conjuntos e ao tipo Set3m 44s](https://app.algaworks.com/aulas/4691/introducao-aos-conjuntos-e-ao-tipo-set)
22. [ ] [Usando conjuntos do tipo HashSet8m 12s](https://app.algaworks.com/aulas/4692/usando-conjuntos-do-tipo-hashset)
23. [ ] [Tabelas de espalhamento (hash tables)6m 17s](https://app.algaworks.com/aulas/4693/tabelas-de-espalhamento-hash-tables)
24. [ ] [Implementando o método hashCode18m 26s](https://app.algaworks.com/aulas/4694/implementando-o-metodo-hashcode)
25. [ ] [Testando a implementação de hashCode com HashSet14m 0s](https://app.algaworks.com/aulas/4695/testando-a-implementacao-de-hashcode-com-hashset)
26. [ ] [Usando conjuntos do tipo TreeSet17m 31s](https://app.algaworks.com/aulas/4696/usando-conjuntos-do-tipo-treeset)
27. [ ] [Usando conjuntos do tipo LinkedHashSet3m 40s](https://app.algaworks.com/aulas/4697/usando-conjuntos-do-tipo-linkedhashset)
28. [ ] [Desafio: conjuntos2m 31s](https://app.algaworks.com/aulas/4698/desafio-conjuntos)
29. [ ] [Introdução aos mapas e ao tipo Map3m 0s](https://app.algaworks.com/aulas/4699/introducao-aos-mapas-e-ao-tipo-map)
30. [ ] [Usando mapas dos tipos HashMap e Hashtable24m 46s](https://app.algaworks.com/aulas/4700/usando-mapas-dos-tipos-hashmap-e-hashtable)
31. [ ] [LinkedHashMap e TreeMap: outras implementações de mapas7m 27s](https://app.algaworks.com/aulas/4701/linkedhashmap-e-treemap-outras-implementacoes-de-mapas)
32. [ ] [Desafio: mapas2m 44s](https://app.algaworks.com/aulas/4702/desafio-mapas)
33. [ ] [Boas práticas: encapsulamento com coleções não-modificáveis23m 13s](https://app.algaworks.com/aulas/4703/boas-praticas-encapsulamento-com-colecoes-nao-modificaveis)
34. [ ] [Coleções imutáveis9m 19s](https://app.algaworks.com/aulas/4704/colecoes-imutaveis)
35. [ ] [Usando a API de List para manipular arrays6m 29s](https://app.algaworks.com/aulas/4705/usando-a-api-de-list-para-manipular-arrays)
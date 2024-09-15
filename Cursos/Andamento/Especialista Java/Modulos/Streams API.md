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
1. [x] [Introdução à Streams API e operações básicas13m 53s](https://app.algaworks.com/aulas/4821/introducao-a-streams-api-e-operacoes-basicas)
2. [x] [Operação intermediária: Stream.filter6m 57s](https://app.algaworks.com/aulas/4822/operacao-intermediaria-streamfilter)
3. [x] [Operação terminal: Stream.forEach3m 30s](https://app.algaworks.com/aulas/4823/operacao-terminal-streamforeach)
4. [x] [Criando o pipeline com encadeamento de operações6m 10s](https://app.algaworks.com/aulas/4824/criando-o-pipeline-com-encadeamento-de-operacoes)
5. [x] [Executando ações intermediárias com o método Stream.peek6m 53s](https://app.algaworks.com/aulas/4825/executando-acoes-intermediarias-com-o-metodo-streampeek)
6. [x] [Operações terminais de curto-circuito: findFirst e findAny7m 40s](https://app.algaworks.com/aulas/4826/operacoes-terminais-de-curto-circuito-findfirst-e-findany)
7. [x] [Testando predicados com Stream.anyMatch, Stream.allMatch e Stream.noneMatch6m 35s](https://app.algaworks.com/aulas/4827/testando-predicados-com-streamanymatch-streamallmatch-e-streamnonematch)
8. [x] [Ordenando elementos de Streams4m 50s](https://app.algaworks.com/aulas/4828/ordenando-elementos-de-streams)
9. [x] [Entendendo o que é uma operação intermediária com estado (stateful)5m 49s](https://app.algaworks.com/aulas/4829/entendendo-o-que-e-uma-operacao-intermediaria-com-estado-stateful)
10. [x] [Aplicando transformações com Stream.map5m 26s](https://app.algaworks.com/aulas/4830/aplicando-transformacoes-com-streammap)
11. [x] [Obtendo um Stream de elementos distintos3m 14s](https://app.algaworks.com/aulas/4831/obtendo-um-stream-de-elementos-distintos)
12. [x] [Achatando um Stream com Stream.flatMap10m 23s](https://app.algaworks.com/aulas/4832/achatando-um-stream-com-streamflatmap)
13. [x] [Usando as especializações de Stream para tipos primitivos8m 58s](https://app.algaworks.com/aulas/4833/usando-as-especializacoes-de-stream-para-tipos-primitivos)
14. [x] [Entendendo as operações de redução com Stream.reduce12m 22s](https://app.algaworks.com/aulas/4834/entendendo-as-operacoes-de-reducao-com-streamreduce)
15. [x] [Reduzindo em BigDecimal e usando a função de combinação12m 5s](https://app.algaworks.com/aulas/4835/reduzindo-em-bigdecimal-e-usando-a-funcao-de-combinacao)
16. [x] [Operações de redução que retornam Optional4m 52s](https://app.algaworks.com/aulas/4836/operacoes-de-reducao-que-retornam-optional)
17. [x] [Operações de redução especiais: sum, average e count9m 11s](https://app.algaworks.com/aulas/4837/operacoes-de-reducao-especiais-sum-average-e-count)
18. [x] [Operações de redução especiais: min e max7m 43s](https://app.algaworks.com/aulas/4838/operacoes-de-reducao-especiais-min-e-max)
19. [x] [Coletando elementos do Stream em lista com Stream.collect9m 2s](https://app.algaworks.com/aulas/4839/coletando-elementos-do-stream-em-lista-com-streamcollect)
20. [x] [Usando coletores padrão da classe Collectors6m 48s](https://app.algaworks.com/aulas/4840/usando-coletores-padrao-da-classe-collectors)
21. [x] [Usando coletores de listas não-modificáveis1m 58s](https://app.algaworks.com/aulas/4841/usando-coletores-de-listas-nao-modificaveis)
22. [x] [Coletando elementos do Stream em mapas3m 45s](https://app.algaworks.com/aulas/4842/coletando-elementos-do-stream-em-mapas)
23. [x] [Gerando mapas agrupados com Collectors.groupingBy5m 30s](https://app.algaworks.com/aulas/4843/gerando-mapas-agrupados-com-collectorsgroupingby)
24. [x] [Gerando mapas agrupados com valores agregados7m 43s](https://app.algaworks.com/aulas/4844/gerando-mapas-agrupados-com-valores-agregados)
25. [x] [Gerando mapas particionados com Collectors.partitioningBy3m 16s](https://app.algaworks.com/aulas/4845/gerando-mapas-particionados-com-collectorspartitioningby)
26. [x] [Outras formas de obter instâncias de Stream18m 48s](https://app.algaworks.com/aulas/4846/outras-formas-de-obter-instancias-de-stream)
27. [x] [Métodos Objects.isNull e Objects.nonNull5m 5s](https://app.algaworks.com/aulas/4847/metodos-objectsisnull-e-objectsnonnull)
28. [x] [Boas práticas: prefira funções em streams sem efeito colateral6m 22s](https://app.algaworks.com/aulas/4848/boas-praticas-prefira-funcoes-em-streams-sem-efeito-colateral)
29. [x] [Desafio: Streams10m 41s](https://app.algaworks.com/aulas/4849/desafio-streams)
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
1. [ ] [Introdução à Date and Time API e ao padrão ISO-860118m 14s](https://app.algaworks.com/aulas/4750/introducao-a-date-and-time-api-e-ao-padrao-iso-8601)
2. [ ] [Instant: representando um momento na linha do tempo15m 55s](https://app.algaworks.com/aulas/4751/instant-representando-um-momento-na-linha-do-tempo)
3. [ ] [LocalDate: representando apenas a data10m 22s](https://app.algaworks.com/aulas/4752/localdate-representando-apenas-a-data)
4. [ ] [LocalTime: representando apenas o horário2m 19s](https://app.algaworks.com/aulas/4753/localtime-representando-apenas-o-horario)
5. [ ] [LocalDateTime: representando data e hora4m 25s](https://app.algaworks.com/aulas/4754/localdatetime-representando-data-e-hora)
6. [ ] [Outras formas de obter instâncias de LocalDate, LocalTime e LocalDateTime6m 48s](https://app.algaworks.com/aulas/4755/outras-formas-de-obter-instancias-de-localdate-localtime-e-localdatetime)
7. [ ] [Formatando data/hora da nova API15m 59s](https://app.algaworks.com/aulas/4756/formatando-datahora-da-nova-api)
8. [ ] [Convertendo de String para objetos temporais9m 20s](https://app.algaworks.com/aulas/4757/convertendo-de-string-para-objetos-temporais)
9. [ ] [Desafio: LocalDate, LocalTime e LocalDateTime2m 5s](https://app.algaworks.com/aulas/4758/desafio-localdate-localtime-e-localdatetime)
10. [ ] [Obtendo campos de objetos temporais e a enum ChronoField9m 2s](https://app.algaworks.com/aulas/4759/obtendo-campos-de-objetos-temporais-e-a-enum-chronofield)
11. [ ] [Alterando campos de objetos temporais com métodos with5m 23s](https://app.algaworks.com/aulas/4760/alterando-campos-de-objetos-temporais-com-metodos-with)
12. [ ] [Adicionando e subtraindo objetos temporais com métodos de conveniência5m 27s](https://app.algaworks.com/aulas/4761/adicionando-e-subtraindo-objetos-temporais-com-metodos-de-conveniencia)
13. [ ] [Calculando objetos temporais com ChronoUnit6m 49s](https://app.algaworks.com/aulas/4762/calculando-objetos-temporais-com-chronounit)
14. [ ] [Desafio: calculadora de parcelas2m 1s](https://app.algaworks.com/aulas/4763/desafio-calculadora-de-parcelas)
15. [ ] [Representando períodos com a classe Period11m 4s](https://app.algaworks.com/aulas/4764/representando-periodos-com-a-classe-period)
16. [ ] [Calculando períodos de objetos temporais9m 13s](https://app.algaworks.com/aulas/4765/calculando-periodos-de-objetos-temporais)
17. [ ] [Representando durações com a classe Duration12m 5s](https://app.algaworks.com/aulas/4766/representando-duracoes-com-a-classe-duration)
18. [ ] [Calculando durações de objetos temporais7m 51s](https://app.algaworks.com/aulas/4767/calculando-duracoes-de-objetos-temporais)
19. [ ] [Desafio: calculando período1m 57s](https://app.algaworks.com/aulas/4768/desafio-calculando-periodo)
20. [ ] [DayOfWeek: representando o dia da semana9m 0s](https://app.algaworks.com/aulas/4769/dayofweek-representando-o-dia-da-semana)
21. [ ] [Year: representando o ano9m 18s](https://app.algaworks.com/aulas/4770/year-representando-o-ano)
22. [ ] [Month: representando o mês12m 24s](https://app.algaworks.com/aulas/4771/month-representando-o-mes)
23. [ ] [MonthDay: representando o dia do mês9m 46s](https://app.algaworks.com/aulas/4772/monthday-representando-o-dia-do-mes)
24. [ ] [YearMonth: representando o mês do ano10m 56s](https://app.algaworks.com/aulas/4773/yearmonth-representando-o-mes-do-ano)
25. [ ] [Alterando campos de objetos temporais com TemporalAdjusters13m 53s](https://app.algaworks.com/aulas/4774/alterando-campos-de-objetos-temporais-com-temporaladjusters)
26. [ ] [Comparando objetos temporais6m 44s](https://app.algaworks.com/aulas/4775/comparando-objetos-temporais)
27. [ ] [Desafio: TemporalAdjuster2m 28s](https://app.algaworks.com/aulas/4776/desafio-temporaladjuster)
28. [ ] [Identificando fusos com ZoneId e ZoneOffset17m 44s](https://app.algaworks.com/aulas/4777/identificando-fusos-com-zoneid-e-zoneoffset)
29. [ ] [Instanciando objetos temporais em um fuso horário específico4m 44s](https://app.algaworks.com/aulas/4778/instanciando-objetos-temporais-em-um-fuso-horario-especifico)
30. [ ] [ZonedDateTime: data/hora com fuso horário16m 4s](https://app.algaworks.com/aulas/4779/zoneddatetime-datahora-com-fuso-horario)
31. [ ] [Calculando e convertendo de/para ZonedDateTime14m 16s](https://app.algaworks.com/aulas/4780/calculando-e-convertendo-depara-zoneddatetime)
32. [ ] [OffsetDateTime e OffsetTime: data e hora com deslocamento do UTC7m 16s](https://app.algaworks.com/aulas/4781/offsetdatetime-e-offsettime-data-e-hora-com-deslocamento-do-utc)
33. [ ] [Desafio: trabalhando com fuso horário3m 24s](https://app.algaworks.com/aulas/4782/desafio-trabalhando-com-fuso-horario)
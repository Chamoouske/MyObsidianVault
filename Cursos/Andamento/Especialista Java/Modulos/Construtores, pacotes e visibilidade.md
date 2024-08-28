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
1. [ ] [Criando e chamando construtores8m 28s](https://app.algaworks.com/aulas/4487/criando-e-chamando-construtores)
2. [ ] [Construtores com parâmetros5m 58s](https://app.algaworks.com/aulas/4488/construtores-com-parametros)
3. [ ] [Sobrecarga de construtores13m 55s](https://app.algaworks.com/aulas/4489/sobrecarga-de-construtores)
4. [ ] [Boas práticas: valide os argumentos de construtores também5m 37s](https://app.algaworks.com/aulas/4490/boas-praticas-valide-os-argumentos-de-construtores-tambem)
5. [ ] [Encadeamento de chamadas de construtores10m 48s](https://app.algaworks.com/aulas/4491/encadeamento-de-chamadas-de-construtores)
6. [ ] [Diagrama de classes: construtores3m 41s](https://app.algaworks.com/aulas/4492/diagrama-de-classes-construtores)
7. [ ] [Desafio: construtores](https://app.algaworks.com/aulas/4493/desafio-construtores)
8. [ ] [Modificador final em variáveis de instância8m 16s](https://app.algaworks.com/aulas/4494/modificador-final-em-variaveis-de-instancia)
9. [ ] [Organizando as classes em pacotes14m 40s](https://app.algaworks.com/aulas/4495/organizando-as-classes-em-pacotes)
10. [ ] [Importando classes de pacotes18m 58s](https://app.algaworks.com/aulas/4496/importando-classes-de-pacotes)
11. [ ] [Modificador de acesso public e default12m 3s](https://app.algaworks.com/aulas/4497/modificador-de-acesso-public-e-default)
12. [ ] [Modificador de acesso private6m 39s](https://app.algaworks.com/aulas/4498/modificador-de-acesso-private)
13. [ ] [Diagrama de classes: visibilidade public, package e private4m 26s](https://app.algaworks.com/aulas/4499/diagrama-de-classes-visibilidade-public-package-e-private)
14. [ ] [Desafio: pacotes e modificadores de acesso](https://app.algaworks.com/aulas/4500/desafio-pacotes-e-modificadores-de-acesso)
15. [ ] [Importando membros estáticos (static import)5m 12s](https://app.algaworks.com/aulas/4501/importando-membros-estaticos-static-import)
16. [ ] [Múltiplas classes não-públicas em um único arquivo6m 20s](https://app.algaworks.com/aulas/4502/multiplas-classes-nao-publicas-em-um-unico-arquivo)
17. [ ] [Conhecendo a documentação JavaDoc do Java SE7m 10s](https://app.algaworks.com/aulas/4503/conhecendo-a-documentacao-javadoc-do-java-se)
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
1. [x] [Estrutura da memória da JVM15m 42s](https://app.algaworks.com/aulas/4479/estrutura-da-memoria-da-jvm)
2. [x] [Call Stack, Stack Memory e Heap Memory10m 20s](https://app.algaworks.com/aulas/4480/call-stack-stack-memory-e-heap-memory)
3. [x] [Informações da Memória Heap com a Runtime API19m 17s](https://app.algaworks.com/aulas/4481/informacoes-da-memoria-heap-com-a-runtime-api)
4. [x] [Configurando a Memória Heap da JVM10m 3s](https://app.algaworks.com/aulas/4482/configurando-a-memoria-heap-da-jvm)
5. [x] [Garbage Collector13m 0s](https://app.algaworks.com/aulas/4483/garbage-collector)
6. [x] [Inalcançabilidade de objetos22m 2s](https://app.algaworks.com/aulas/4484/inalcancabilidade-de-objetos)
7. [x] [Quando esgota a Memória Heap: OutOfMemoryError9m 19s](https://app.algaworks.com/aulas/4485/quando-esgota-a-memoria-heap-outofmemoryerror)
8. [x] [Boas práticas: remova referências de objetos não usados](https://app.algaworks.com/aulas/4486/boas-praticas-remova-referencias-de-objetos-nao-usados)
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
- [x] 01- Criando o primeiro programa Java
- [x] 02- Compilando e executando um programa Java
- [x] 03- Desafio: correção de erros
- [x] 04- Escrevendo comentários no código
- [x] 05- Conhecendo e usando convenções de código
- [x] 06- Palavras reservadas
- [x] 07- Trabalhando com variáveis
- [x] 08- Operadores aritméticos
- [x] 09- Desafio: variáveis e operadores aritméticos
- [x] 10- Abreviando operadores aritméticos
- [x] 11- Operadores de incremento de decremento
- [x] 12- Tipos primitivos: boolean, char, byte e short
- [x] 13- Tipos primitivos: int e long
- [x] 14- Tipos primitivos: float e double
- [x] 15- Conversão de tipos primitivos
- [x] 16- Desafio: tipos primitivos e conversão
- [x] 17- Promoção aritmética
- [x] 18- Desafio: promoção aritmética
- [x] 19- Trabalhando com String
- [x] 20- Usando sequências de escape
- [x] 21- Formatando a saída com printf
- [x] 22- Recebendo entrada de dados
- [x] 23- Desafio: String, entrada de dados, printf, etc
- [x] 24- Usando JShell: o REPL do Java
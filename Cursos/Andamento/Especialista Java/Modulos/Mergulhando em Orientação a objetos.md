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
- [x] 01- O paradigma da Programação Orientada a Objetos (POO)
- [x] 02- Entendendo o conceito de classes e objetos
- [x] 03- Criando uma classe com atributos
- [x] 04- Instanciando objetos
- [x] 05- Acessando atributos de objetos
- [x] 06- Conhecendo o diagrama de classes da UML
- [x] 07- Desafio: instanciando objetos e acessando os atributos
- [x] 08- Composição de objetos
- [x] 09- Atribuindo o objeto na composição
- [x] 10- Diagrama de classes: associação, agregação e composição
- [x] 11- Valores padrão e inicialização de variáveis de instância
- [x] 12- Inicialização de objetos em variáveis de instância
- [x] 13- Caindo a ficha: variáveis referenciam objetos
- [x] 14- Criando e invocando um método
- [x] 15- Implementando a lógica do método
- [x] 16- IntelliJ IDEA: debug de chamadas de métodos
- [x] 17- Métodos com retorno
- [x] 18- Implementando métodos menores e evitando duplicação de código
- [x] 19- Saindo do método com a cláusula return
- [x] 20- Métodos que retornam objetos
- [x] 21- Refatorando para tornar uma classe mais rica
- [x] 22- Discutindo nome e responsabilidade da classe
- [x] 23- Métodos com argumentos
- [x] 24- Passando objetos como argumentos de métodos
- [x] 25- Desafio: composição de objetos e métodos
- [x] 26- Diagrama de classes: métodos e dependências
- [x] 27- Métodos que alteram variável de instância
- [x] 28- Métodos que alteram o valor de parâmetro do tipo primitivo
- [x] 29- Métodos que alteram o estado do objeto recebido como parâmetro
- [x] 30- Usando a palavra-chave this
- [x] 31- Atributos de classe com o modificador static
- [x] 32- Método de instância alterando variável estática
- [x] 33- Métodos de classe (estáticos)
- [x] 34- Método estático acessando membro de instância
- [x] 35- Desafio: membros estáticos
- [x] 36- Declarando constantes com static e final
- [x] 37- Modificador final em variáveis locais
- [x] 38- Sobrecarga de métodos
- [x] 39- Inferência de tipo de variável local
- [x] 40- Desafio: modificador final em variáveis locais
- [x] 41- Desafio: sobrecarga de métodos
- [x] 42- Desafio: inferência de tipo de variável local
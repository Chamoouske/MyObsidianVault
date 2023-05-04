---
banner: "https://images5.alphacoders.com/750/750261.png"
banner_y: 0.328
---

## [[Animes]]

## Tasks
```button
name Nota Task
type note(Untitled) template
action NewMainTaskGTRR
templater true
```
```dataviewjs
const {createButton} = app.plugins.plugins['buttons'];
const {update} = this.app.plugins.plugins['metaedit'].api;

async function setButtonColorDateTask(value){
	
	
	return "red"
}

dv.header(2, 'Lista de Tarefas')
const pages = dv.pages('"Tasks"');
for(let group of pages.groupBy(t=>t.project)){
	dv.header(4, group.key)
	dv.table(
		['Task', 'Status', 'Priority', 'Due Date', ''],
		group.rows.sort(t=>t.status)
			.where(t=>!(t.status=='Completed'))
			.map(t => {
				const daysRemaining = (new Date(t.until) - new Date()) / (1000 * 60 * 60 * 24);
				let color;
				if(daysRemaining < 1){
					color = "red";
				}else if(daysRemaining < 4){
					color = "purple";
				}else{
					color = "green";
				}
				return [
					t.file.link,
					t.status,
					t.priority,
					t.until,
					createButton({
						app,
						el: this.container,
						args: {
							name: t.status == "To Do" ? "In Progress" : "Completed",
							color: t.until ? color : "green"
						},
						clickOverride: {
							click: update,
							params: [
								'status',
								t.status == "To Do" ? "In Progress" : "Completed",
								t.file.path
							]
						}
					})
				]
			})
	)
}
```

## [[Vídeos pra assistir]]

> [!warning] Adicionar vídeos na lista
> Para adicionar um novo vídeo, acesse o arquivo [[Vídeos pra assistir]] e clique no botão _Add Vídeo_.
```dataview
TASK
FROM "Youtube"
WHERE !completed
```

## Guias de Ajuda
```dataview
LIST
FROM "Ajuda" and #Ajuda
```

## Guia de Estudos
```dataview
LIST
FROM "Guias de Estudo" and #guia/estudo
```
```button
name Novo Guia da Estudos
type note(Guias de Estudo/Untitled) template
action Guia_estudos
templater true
```

## Roteiros
```dataview
LIST
FROM "Roteiros" and #roteiros
```


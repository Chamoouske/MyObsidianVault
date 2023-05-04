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

function createDivPercentage(percent){
	let style = `
		width:100%;
		border:1px solid green;
		text-align:center;
		border-radius:0.7rem;
		background-image:linear-gradient(to right, rgb(0,130,0,1) ${percent<100?percent-10:percent}%,rgb(0,0,0,0) ${percent<100?percent+20:0}%);`;
	return `<div style="${style}">${percent}%</div>`
}

const pages = dv.pages('"Tasks"');
for(let group of pages.where(t=>!(t.status=='Completed')).groupBy(t=>t.project)){
	dv.header(3, group.key)
	dv.table(
		['Task', 'Status', 'Priority', 'Due Date', 'Progress', ''],
		group.rows.sort(t=>((t.Complete / t.Total || 0) * 100))
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
				const progress = ((t.Complete / t.Total || 0) * 100)
				return [
					t.file.link,
					t.status,
					t.priority,
					t.until,
					createDivPercentage(progress.toFixed(2)),
					createButton({
						app,
						el: this.container,
						args: {
							name: t.status == "To Do" ? "In Progress" : " Complete ",
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

dv.header(3, "All Tasks")
dv.table(
	['Task', 'Project', 'Status', 'Priority', 'Due Date', 'Progress'],
	pages.sort(t=>((t.Complete / t.Total || 0) * 100))
		.map(t => {
				const progress = ((t.Complete / t.Total || 0) * 100)
				return [
					t.file.link,
					t.project,
					t.status,
					t.priority,
					t.until,
					createDivPercentage(progress.toFixed(2))
				]
			}
		)
)
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


---
banner: "https://images5.alphacoders.com/750/750261.png"
banner_y: 0.328
---

## [[Animes]]

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


---
celular: "260"
parcela-celular: "8"
material-alcie: "190"
parcela-material-alcie: "4"
spotfy: "22"
google-storage: "7"
sapato-supermoda: "39"
parcela-sapato-supermoda: "6"
mochila-supermoda: "24"
parcela-mochila-supermoda: "2"
---

```dataviewjs
let totalDividas = 0;
//totalDividas += (dv.current()?.celular || 0) * (dv.current()['parcela-celular'] || 0);

totalDividas += (dv.current()['material-alcie'] || 0) * (dv.current()['parcela-material-alcie'] || 0);

totalDividas += (dv.current().spotify || 0);
totalDividas += (dv.current()['google-storage'] || 0);

totalDividas += (dv.current()['sapato-supermoda'] || 0) * (dv.current()['parcela-sapato-supermoda'] || 0);
totalDividas += (dv.current()['mochila-supermoda'] || 0) * (dv.current()['parcela-mochila-supermoda'] || 0);

dv.header(2, `Total dividas: R$${totalDividas}`);
```
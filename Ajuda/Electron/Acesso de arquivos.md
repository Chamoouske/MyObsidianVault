No `main.js` adicionar o seguinte código:
```js
const { ipcMain } = require('electron');

const appPath = () => {
	switch(process.plataform){
		case 'darwin':
			return path.join(process.env.HOME, 'Library', 'Application Support');
		case 'win32':
			return path.join(process.env.APPDATA);
		case 'linux':
			return path.join(process.env.HOME);
	}
}

ipcMain.on('NAME_EVENT', async (args) => {
	functionToExecute(args);
})
```
No _processo de renderização_ adicione o seguinte código:
```js
const { ipcRenderer } = require('electron');
ipcRenderer.sendSync('NAME_EVENT', args);
```
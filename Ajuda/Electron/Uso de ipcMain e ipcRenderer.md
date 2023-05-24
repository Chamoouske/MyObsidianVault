No `main.js` seguir o exemplo código:
```js
const { ipcMain } = require('electron');

function writeFile(filename, inData){
	const path = electron.app.getPath('userData');
	fs.writeFile(fullPath, inData, (err)=>{
		if(err) throw err;
	});
}

async function readFile(filename){
	const path = electron.app.getPath('userData');
	const buf = await fs.promises.readFile(`${path}/${filename}`);
	return buf;
}

ipcMain.handle('write-file', async (event, args) => {
	writeFile(args.filename, args.inData);
})

ipcMain.handle('read-file', async (event, args) => {
	return await readFile(args.filename);
})
```
No `preload.js` adicione o seguinte código:
```js
const { contextBridge, ipcRenderer } = require("electron");

contextBridge.exposeInMainWorld(
	"electronAPI", {
		readFile: async () => {
			return ipcRenderer.invoke('read-file', { filename: 'file.txt' });
		},
		writeFile: async (data) => {
			return ipcRenderer.invoke('write-file', { filename: 'file.txt', data: data });
		},
		}
	}
);
```

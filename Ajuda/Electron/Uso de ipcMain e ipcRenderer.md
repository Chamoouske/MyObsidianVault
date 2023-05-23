No `main.js` seguir o exemplo código:
```js
const { ipcMain } = require('electron');

function writeFile(filename, inData){
	const fullPath = path.join(electron.app.getPath('userData'), "\\", fileName);
	fs.writeFile(fullPath, inData, (err)=>{
		if(err) throw err;
	});
}

async function readFile(filename){
	const path = electron.app.getPath('userData');
	const buf = await fs.promises.readFile(`${path}/${filename}`);
	return buf
}

ipcMain.on('write-user-data', async (event, args) => {
	writeFile(args.filename, args.inData);
})

ipcMain.handle('read-user-data', async (event, args) => {
	return await readFile(args.filename);
})
```
No _processo de renderização_ adicione o seguinte código (Nesse caso, **não tem retorno** do evento chamado):
```js
const { ipcRenderer } = require('electron');
ipcRenderer.sendSync('write-user-data', {filename, inData});
```
No caso de eventos que **necessita de retorno**, utiliza-se:
```js
const { ipcRenderer } = require('electron');
ipcRenderer.invoke('read-user-data', {filename}).then(res => doSomething());
```

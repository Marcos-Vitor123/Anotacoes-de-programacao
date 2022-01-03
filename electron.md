<h1>Anotações de estudos e pesquisas sobre o Eléctron</h1>

`npm init -y` Gerar o package.json onde gerencia as configurações do app. <b>OBS:</b> O nome da pasta do projeto não pode ter acento e se houver algum espaço no nome, é preciso colocar um traço. Se não, não funciona.<br>
`npm install --save-dev electron` Instalar o <b>Eléctron</b> no seu projeto <b>OBS:</b> Colocar `@` + o `<número da versão>` desejada, caso queira uma versão anterior específica. Mas, se quiser a versão mais atualizada. Nesse caso, não coloque nada!<br> 
`node_modules/.bin/electron main.js` Abrir a janela da aplicação na tela.<br>
`npm install --save` + a `<dependência>` preferida => Usado para ficar no seu projeto definitivo. Isso, usando qualquer dependência como por ex: bootstrap, jquery, popper.js etc. `npm install --save bootstrap jquery popper.js`.<br>
`npm install --save-dev` + a `<dependência>` preferida => Usado somente para desenvolver naquele projeto. Como por ex: o <b>Eléctron</b>. `npm install --save-dev electron`.<br>
<b>A barra de ferramentas</b> que carrega junto com a aplicação no topo. Ajuda no desenvolvimento como por ex: a função do "reload" ou o atalho "CTRL + R" é para recarregar a aplicação para fins de testes. É indicado retirar ela somente no término do app.</br>
`"start": electron main.js,` Adicionar o comando start no corpo do arquivo package.json logo abaixo de `"script": { ... }` substitui o código `node_modules/.bin/electron main.js` de chamar a aplicação. Logo após isso é só digitar `npm start` para abrir o app. Ex:
```
"scripts": {
    "start": "electron main.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
```
`cursor: default;` Evita do mouse ficar selecionando letras no app.<br>
`icon: __dirname + '/128.png'` Adicionar ícone no app. Colocar logo abaixo de `height: 205,` no arquivo main.js dentro da `const creatWindow(){...}`. Ex: 
  ```
    mainWindow = new BrowserWindow({
        width: 282,
        height: 205,
        icon: __dirname + '/128.png'
    });
 ``` 
`mainWindow.setMenuBarVisibility(false);` Para retirar barra de ferramentas padrão do windows no app. Colocar dentro da função `createWindow` Ex:
```
    function createWindow() {

    mainWindow = new BrowserWindow({
        width: 282,
        height: 205,
        icon: __dirname + '/128.png'
    });

    mainWindow.setMenuBarVisibility(false);
    mainWindow.loadFile(__dirname + '/index.html');
    mainWindow.on('closed', function () {
        mainWindow = null;
    })
}
```
`resizable: false` Limita o tamanho da largura e altura da aplicação no tamanho configurado no arquivo main.js. Ou seja, não maximiza. Apenas minimiza e fecha.<br>
`npm install electron-packager -g` Para instalar o compilador no seu projeto.<br>
<b>Para compilar</b> Basta colocar os comandos abaixo: <br> 
`electron-packager` --> para chamar o compilador + <br>
`Origem do diretório` Ex: `./` --> para selecionar o diretório do projeto
`<nome do programa>` Ex: `NomeDoPrograma` + <br>
`--platform-<nome da plataforma ou sistema operacional>` Ex: `--platform=win32` + <br>
`--arch-<arquitetura se é x86 ou x64 do sistema operacional destinado>` Ex: `--arch=x64` + <br>
`--out<destino ou pasta de onde o programa compilado vai ficar>` Ex: `--out ./` --> Selecionei o própio diretório do projeto como destino + <br>
`--version <número da versão>` Ex: `--version 1.0.0` + <br>
`--overwrite` E finalmente esse comando para substituir os arquivos existentes cada vez que instalar o programa no mesmo local. Se não colocar ele, aí dá um erro dizendo que aqueles arquivos já existem. Isso bom caso atualize o programa várias vezes não gerando esse erro. <br>

```
electron-packager ./ nomeDoPrograma --platform=win32 --arch=x64 --out ./ --version 1.0.0 --overwrite
```
=> Para automotizar esses comandos acima é só acrescentar eles no arquivo package.json. Ex: <br>
```
"scripts": {
    "start": "electron main.js",
    "build": "electron-packager ./ nomeDoPrograma --platform=win32 --arch=x64 --out ./ --version 1.0.0 --overwrite",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
```
=> E depois é só chamar digitando `npm run build`. <br>


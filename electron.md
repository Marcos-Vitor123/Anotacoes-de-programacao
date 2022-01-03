<h1>Anotações de estudos e pesquisas sobre o Eléctron</h1>

`npm init -y` Gerar o package.json onde gerencia as configurações do app. <b>OBS:</b> O nome da pasta do projeto não pode ter acento e se houver algum espaço no nome, é preciso colocar um traço. Se não, não funciona.<br>
`npm install --save-dev electron` Instalar o <b>Eléctron</b> no seu projeto <b>OBS:</b> Colocar `@` + o `<número da versão>` desejada, caso queira uma versão anterior específica. Mas, se quiser a versão mais atualizada. Nesse caso, não coloque nada!<br> 
`node_modules/.bin/electron main.js` Abrir a janela da aplicação na tela.<br>
`npm install --save` + a `<dependência>` preferida => Usado para ficar no seu projeto definitivo. Isso, usando qualquer dependência como por ex: bootstrap, jquery, popper.js etc. `npm install --save bootstrap jquery popper.js`.<br>
`npm install --save-dev` + a `<dependência>` preferida => Usado somente para desenvolver naquele projeto. Como por ex: o <b>Eléctron</b>. `npm install --save-dev electron`.<br>
<b>A barra de ferramentas</b> que carrega junto com a aplicação no topo. Ajuda no desenvolvimento como por ex: a função do "reload" ou o atalho "CTRL + R" é para recarregar a aplicação para fins de testes. É indicado retirar ela somente no término do app.</br>
`"start": electron main.js,` Adicinar o comando start no corpo do arquivo package.json logo abaixo de `"script": { ... código restante ... }` substitui o código `node_modules/.bin/electron main.js` de chamar a aplicação. Logo após isso é só digitar `npm start` para abrir o app.<br>
`cursor: default;` Evita do mouse ficar selecionando letras no app.
`icon: __dirname + '/128.png'` Adicionar ícone no app. Colocar logo abaixo de `height: 205,` no arquivo main.js dentro da `const creatWindow(){...}`. Ex: 
  ```
    mainWindow = new BrowserWindow({
        width: 282,
        height: 205,
        icon: __dirname + '/128.png'
    });
 ``` 

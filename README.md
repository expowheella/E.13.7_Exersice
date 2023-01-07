        $ npm init
        $ mkdir crs
        $ cd crs && index.js
        $ mkdir js
        $ cd js && touch common.js
        $ npm install webpack webpack-cli webpack-dev-server path --save-dev
        $ npm install html-webpack-plugin
        $ npm run dev
        $ npm install --save-dev webpack-merge

<hr>

* make sure to import <i>common.js</i> into <i>index.js</i> with extension <i>".js"</i> in import statement

        import './js/common.js'

* make sure to use <i>type="module"</i> in <i>index.html</i> 
        
        <script type="module" src="./src/index.js"></script>

<hr>
<h2>Настройка запуска на разных окружениях (dev, prod)</h2>
https://webpack.js.org/guides/production/

<hr>
<h2>JSON-server</h2> 

        $ npm install -g json-server
        $ touch db.json
        $ json-server --watch db.json
<hr>
<h2>Hooks for pre-commit linter</h2>
    
        $ npm install husky --save-dev
        $ npm pkg set scripts.prepare="husky install"
        $ npm run prepare

Add a script for a linter to padkage.json.
Add a task to husky for running that script:

        $ npx husky add .husky/pre-commit "npm run lint"        
        $ git add .husky/pre-commit

Install linter 

        $ npm install -g eslint
        $ npm init @eslint/config

Finally, commit

        $ git commit -m "test commit"


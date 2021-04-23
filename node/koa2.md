#### nodemon+vscode配置

```json
{
    "name":"nodemon",
    "runtimeExecutable":"nodemon",
    "program":"${workspaceFolder}/app.js",
    "restart":true,
    "console":"integratedTerminal",
    "internalConsoleOptions":"neverOpen"
}
```

#### requireDirectory实现路由自动加载

```js
const modules = requireDirectory(module,'./api',{visit:whenLoadModule})
//process.cwd() 获取绝对路径

function whenLoadModule(obj){
    if(obj instanceof Router){
        app.use(obj.routes)
    }
}
```

#### package.json

```json
koa
koa-bodyparser
koa-router
koa-static
lodash
mysql2
npm-check
require-directory
sequelize
validator
axios
basic-auth
bcryptjs
jsonwebtoken
```

core：http-exception，init

middlewares：exception

api：v1，v2  

#### 配置文件与在终端显示异常

```js
module.exports={
    environment:'dev'
}
```


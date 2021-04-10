# Vite2

> Vite 是一个开发构建工具，开发过程中利用浏览器native ES Module特性按需导入源码，预打包依赖。
>
> 特点：启动快；更新快
>
> （无论代码体积有多大，）

### 创建vite2项目



```powershell
npm init @vitejs/app
or
yarn create @vitejs/app
```

### 静态资源引入

```js
src="./assets/logo.png" // 解析为绝对地址
```

### 样式引入

```js
:class="$style.logo"
```

```css
<style module>
.logo{
    
}
</style>
```

- 加载模块化css，创建App.module.css

```js
import classes from './App.module.css'
:class="classes.logo"
```

- 引入autoprefixer

```powershell
npm i -D autoprefixer
```

```js
// postcss.config.js
module.exports = {
    plugins: [
        require('autoprefixer')
    ]
}
```

### TS引入

typescript需要限制版本

### 代理

```js
export default defineConfig({
	server:{
    	proxy:{
        	"/api":{
            	target:"http://",
            	changeOrigin:true,
            	rewrite:(path)=>path.replace(/^\/api/,"")
        	}
    	}
	}
})
```

### 数据mock

```powershell
npm i mockjs -S
npm i vite-plugin-mock -D
```

引入插件`vite.config.js`

```js
import {viteMockServe} from 'vite-plugin-mock'
export default defineConfig({
    plugins:[ viteMockServe({}) ]
})
```

```js
export default[
    {
        url:'',
        method:'',
        response:req=>{
            return{
                code:0,
                data:[]
            }
        }
    }
]
```

### 代码规范

```json
//package.json
{
  "scripts": {
    "lint": "eslint \"src/**/*.{js,vue}\""
  },
  "devDependencies": {
    "@vue/eslint-config-prettier": "^6.0.0",
    "eslint": "^7.20.0",
    "eslint-plugin-prettier": "^3.3.1",
    "eslint-plugin-vue": "^7.6.0",
    "prettier": "^2.2.1"
  }
}
```


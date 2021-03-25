## vite2.0 创建

```powershell
$npm init @vitejs/app
or
$yarn create @vitejs/app
```

## 依赖安装

#### ESLint

```powershell
npm i eslint prettier eslint-plugin-prettier eslint-plugin-vue babel-eslint @vue/eslint-config-prettier --save-dev
```

```json
//package.json
{
  "scripts": {
    "lint": "eslint \"src/**/*.{js,vue}\""
  },
  "devDependencies": {
    "@vue/eslint-config-prettier": "^6.0.0",
    "babel-eslint": "^10.1.0",
    "eslint": "^7.21.0",
    "eslint-plugin-prettier": "^3.3.1",
    "eslint-plugin-vue": "^7.7.0",
    "prettier": "^2.2.1",
  }
}

```

- 创建eslint配置文件：

1. *.eslintrc*：配合eslint插件可以友好的提示可以使用的选项
2. *.eslintrc.js*：可以增加动态配置

- extends

1. `eslint:recommended`：eslint建议规则
2. `plugin:vue/vue3-essential`：vue3核心的lint规则
3. `@vue/prettier`：prettier建议规则

```js
//.eslintrc.js
module.exports = {
  root: true,
  env: {
    browser: true,
    es6: true,
    node: true,
  },
  extends: ["eslint:recommended", "plugin:vue/vue3-essential", "@vue/prettier"],
  globals: {
    Atomics: "readonly",
    SharedArrayBuffer: "readonly",
  },
  parser: "vue-eslint-parser",
  parserOptions: {
    parser: "babel-eslint",
    ecmaVersion: 2018,
    sourceType: "module",
  },
  plugins: ["typescript", "vue", "html"],
  rules: {
    "no-console": process.env.NODE_ENV === "production" ? "warn" : "off",
    "no-condebuggersole":
      process.env.NODE_ENV === "production" ? "warn" : "off",
    "no-undef": 1, //不能有未定义的变量
    "no-use-before-define": 2, //未定义前不能使用
    "vue/no-multiple-template-root": 0,
    "no-unused-vars": [2, { vars: "all", args: "after-used" }], //不能有声明后未被使用的变量或参数
    "no-multiple-empty-lines": "error", // 不允许多个空行
  },
};

```



#### Typscript 

```json
//tsconfig.json
{
  "compilerOptions": {
    "target": "esnext",
    "module": "esnext",
    "moduleResolution": "node",
    "isolatedModules":true,
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "experimentalDecorators": true,
    "lib": ["esnext", "dom"],
    "types": ["vite/client", "node"],
    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"]
    }
  },
  "include": ["src/**/*.ts", "src/**/*.d.ts", "src/**/*.tsx", "src/**/*.vue"],
  "exclude": ["node_modules", "dist", "**/*.js"]
}

```

#### Sass



```powershell
npm i eslint eslint-config-prettier eslint-plugin-vue prettier-eslint --save-dev
```

```powershell
npm i typescript @typescript-eslint/parser @typescript-eslint/eslint-plugin --save-dev
```

```powershell

```


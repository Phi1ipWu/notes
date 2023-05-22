<h1>TypeScript项目配置</h1>


<h3>1. npm 初始化项目</h3>
<p>npm init</p>


<h3>2. 安装 TypeScript</h3>
<p>npm install typescript --save-dev</p>
<p>npx tsc --version</p>


<h3>3. 安装 Node.js 内置类型声明</h3>
npm install @types/node --save-dev


<h3>4. 初始化 tsconfig</h3>
npx tsc --init --rootDir src --outDir build --esModuleInterop --resolveJsonModule --lib es6 --module commonjs --allowJs true --noImplicitAny true


<h3>5. 创建 src/main.ts</h3>
mac: 
mkdir src
echo 'console.log("Hello world!")' > src/main.ts

win:
md src
copy con src\main.ts
console.log("Hello world!")
^z


<h3>6. 通过 npx tsc 来编译项目工程 (编译后在 build 目录下可以看到 js 文件)</h3>
npx tsc
node ./build/main.js


<h3>7. 修改 package.json，来支持 npm run build 和 npm start 命令</h3>
"scripts": {
  "build": "tsc",
  "start": "tsc && node ./build/main.js"
},


<h3>附录</h3>
1. npm install有以下几种方式：
npm install moduleName # 安装模块到项目目录下
npm install -g moduleName # -g 的意思是将模块安装到全局，具体安装到磁盘哪个位置，要看 npm config prefix 的位置。
npm install --save moduleName # --save 的意思是将模块安装到项目目录下，并在package文件的dependencies节点写入依赖。
npm install --save-dev moduleName # --save-dev 的意思是将模块安装到项目目录下，并在package文件的devDependencies节点写入依赖。

总结为一句话：运行时需要用到的包使用––save，否则使用––save-dev。



引用出处：
https://shixiongfei.com/typescript-startup.html

tsconfig配置参考：
https://www.typescriptlang.org/

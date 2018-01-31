# react-hello-world
A hello-world app using react
# package.json
{
  "name": "zzz",
  "version": "1.0.0",
  "description": "",
  "main": "a.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "webpack"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "babel-cli": "^6.26.0",
    "babel-loader": "^7.1.2",
    "babel-preset-env": "^1.6.1",
    "babel-preset-react": "^6.24.1",
    "react": "^16.2.0",
    "react-dom": "^16.2.0",
    "webpack": "^3.10.0"
  }
}
# .babelrc
{
  	"presets": ["env",'react']
}
# webpack.config.js
module.exports = { 	//注意这里是exports不是export
    	entry: 	__dirname + "/app/main.js",//唯一入口文件，就像Java中的main方法
    	output: {//输出目录
        	path: __dirname + "/build",//打包后的js文件存放的地方
        	filename: 	"bundle.js"//打包后的js文件名
    	},
    	module: {
        //loaders加载器
	        loaders: [
	            {
	                test: /\.(js|jsx)$/, 		//一个匹配loaders所处理的文件的拓展名的正则表达式，这里用来匹配js和jsx文件（必须）
	                exclude: /node_modules/, 	//屏蔽不需要处理的文件（文件夹）（可选）
	                loader: 'babel-loader' 		//loader的名称（必须）
	            }
	        ]
    }
};
# a.html
<!DOCTYPE html>
<html>
<head>
	<title></title>

</head>
<body>
	<div id="content"></div>
</body>
<script src="./build/bundle.js"></script>
</html>
# app/main.js
//main.js
import React 		from 'react';
import ReactDom 	from 'react-dom';
import Component1 	from '../components/Component1.jsx';
ReactDom.render(
    	<Component1 />,
    	document.getElementById('content')
);
# components/Componet1.jsx
import React from 'react';
class 	Component1 extends React.Component {
    	render() {
        	return (
            		<div>Hello World!</div>
        	)
    }
}
export default Component1; //导出组件

## 1. 复制一个 .gitignore文件  到新建的目录
## 2. 输入webpack的配置
~~
npm init -y
npm i webpack webpack-cli -g
npm i webpack webpack-cli --save-dev
~~
## 3. 建立基本文件
src/index.css , index.js


在 webpack.config.js 里建立新内容
module.exports = {
    /* 模式 */
    mode: "development",
    /* 人口文件 */
    entry: "./src/index.js",
    /* 出口文件 */
    output: {
        filename: "[name].bundle.js",
        path: path.resolve(__dirname, 'dist')
    },
    devServer: {
        contentBase: './dist'
    },
}
## 4. 处理css
装依赖
npm i style-loader css-loader --save-dev

//webpack.config.js
module.exports ={
    module:{
        rules:[
            {
                test:/\.css$/,
                user:['style-loader','css-loader']
            }
        ]
    }
}
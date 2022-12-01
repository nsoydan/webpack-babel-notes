# webpack-babel-notes
notes for using webpack and babel for react

npm install --save-dev webpack webpack-cli
or

yarn add webpack webpack-cli
yarn add @bable/core @babel/preset-env @babel/preset-react babel-loader

yarn add style-loader css-loader
yarn add html-loader html-webpack-plugin

in package.json file :

scripts -> "build" : "webpack --mode production"

webpack.config.js file under root folder

const htmlWebPackPlugin= require('html-webpack-plugin')

module.exports ={
module : {
rules : [
{
test : /\.(js|jsx)$/,
                    exclude: /node_modules/,
                    use :   {
                            loader : 'babel-loader'
                            }
                },
                {
                    test : /\.css$/,
  use : {
loader : ['style-loader', 'css-loader']
},
}
{
test: /\.html$/,
use: {
loader: 'html-loader'
}
}
],
}
plugins : [
new htmlWebPackPlugin({
template: './index.html'
})
]
}

app -> app.jsx olarak eklenmeli !!

add .babelrc file in root directory

{
"presets" : ["@babel/preset-env, "@babel/preset-react"]
} // es6 ->es5 //react->es5

https://webpack.js.org/concepts/

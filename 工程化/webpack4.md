Webpack4
>第四版做了进行了工程化的变革

## 开发环境 VS v3

在 webpack 4+ 中，你可以使用 mode 选项：

`module.exports = {
  mode: 'production'
}`


但是在 webpack 3 及其更低版本中，你需要使用 DefinePlugin：

```var webpack = require('webpack')

module.exports = {
  // ...
  plugins: [
    // ...
    new webpack.DefinePlugin({
      'process.env': {
        NODE_ENV: JSON.stringify('production')
      }
    })
  ]
}```
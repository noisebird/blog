### webpack 常用到的插件
1. webpack配置中的context属性

    context 可以指定 entry 入口文件的工作目录
    ```
    const path = require('path');
    
    module.exports = {
        context: path.resolve(__dirname, 'app'),
        entry: './main.js',
        output: {
            path: path.resolve(__dirname, 'dist'),
            filename: 'bundle.js'
        }
    }
    ```
    入口文件的main.js 其实就是在app目录下去找main.js文件
    
2. webpack 配置中的entry属性

    entry 顾名思义就是入口的意思。在webpack中我们需要指定整个项目打包的开始文件，也就是入口文件，webpack会根据入口文件中的依赖一层一层的搜索依赖，然后进行打包操作。
    对于入口文件的设置，我们一般有三种情况：
    + 对于单页应用（entry 的value为字符串）
        ```
        module.exports = {
            entry: './main.js',
            output: {
                path: __dirname,
                filename: 'bundle.js'
            }
        }
        ```
    + 对于多页应用（entry 的value为对象）
        ```
        module.exports = {
            entry: {
                one: './main1.js',
                two: './main2.js',
                'path/to/main': './main3.js'
            },
            output: {
                path: __dirname,
                filename: '[name].js'
            }
        }
        ```
    + 对于单页应用，但是有多个js引用入口（entry 的value为数组）
        ```
        module.exports = {
            entry: ['./main1.js', './main2.js'],
            output: {
                path: __dirname,
                filename: 'bundle.js'
            }
        }
        ```
      这里能够将多个入口打包成一个bundle.js文件

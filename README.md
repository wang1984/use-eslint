## 注意 安装的包名不能和package的title名重名

>  npm install eslint --save-dev
>  eslint --init 生成 .eslintrc.js 文件
>  新建 .eslintignore 文件 这是需要忽略忽略检查的文件
>  eslint yourfile.js  yourfile.js是你需要测试的js文件

##EsLint还提供了error的级别，对应数字，数字越高错误的提示越高.
0.  代码错误不提示、
1.  代表警告提醒但不影响现有编译、
2.  error会抛出错误。

##配置文件 .eslintrc.js
	module.exports = {
	    //此项是用来告诉eslint找当前配置文件不能往父级查找
	    root: true, 
	    //此项是用来指定eslint解析器的，解析器必须符合规则，babel-eslint解析器是对babel解析器的包装使其与ESLint解析
	    parser: 'babel-eslint',
	    //	此项是用来指定javaScript语言类型和风格，sourceType用来指定js导入的方式，默认是script，此处设置为module，指某块导入方式
	    parserOptions: {
	        sourceType: 'module'
	    },
	    //此项指定环境的全局变量，下面的配置指定为浏览器环境
	    env: {
	        browser: true,
	    },
	    // https://github.com/feross/standard/blob/master/RULES.md#javascript-standard-style
	    // 此项是用来配置标准的js风格，就是说写代码的时候要规范的写，如果你使用vs-code我觉得应该可以避免出错
	    extends: 'standard',
	    // required to lint *.vue files
	    // 此项是用来提供插件的，插件名称省略了eslint-plugin-，下面这个配置是用来规范html的
	    plugins: [
	        'html'
	    ],
	    // add your custom rules here
	    // 下面这些rules是用来设置从插件来的规范代码的规则，使用必须去掉前缀eslint-plugin-
	    // 主要有如下的设置规则，可以设置字符串也可以设置数字，两者效果一致
	    // "off" -> 0 关闭规则
	    // "warn" -> 1 开启警告规则
	    // "error" -> 2 开启错误规则
	    // 了解了上面这些，下面这些代码相信也看的明白了
	    'rules': {
	        // allow paren-less arrow functions
	        'arrow-parens': 0,
	        // allow async-await
	        'generator-star-spacing': 0,
	        // allow debugger during development
	        'no-debugger': process.env.NODE_ENV === 'production' ? 2 : 0
	    }
	}

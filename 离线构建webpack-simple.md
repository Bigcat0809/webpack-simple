自己用vue-cli构建项目时，vue init webpack your-ProjectName报错;
在没有设置代理的情况下;在简书上看到被人给的方案是离线构建;解决办法是:
下载webpack-simple到本地下载地址：https://github.com/vuejs-templates
然后解压，把文件拷贝到你电脑的.vue-templates所在的目录--例如这是我的.vue-templates目录：C:\Users\Administrator\.vue-templates
然后构建你的vue项目：
vue init webpack-simple your-ProjectName --offline
cd your-ProjectName
npm install/cnpm install
npm run dev

注意：webpack-simple如何引入css文件
webpack-simple是一个简化版本，需要手动配置。
在该项目目录下npm/cnpm  install css-loader style-loader --save-dev，下载完后要在webpack.config.js的rules中加入一句css规则的代码
{
    test:'/\.css$/',
    loader:'style-loader!css-loader',
}
之后在src/assets/main.js文件中输入import 'css路径'即可。如：
import './assets/common.css

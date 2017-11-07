自己用vue-cli构建项目时，vue init webpack your-ProjectName报错;
在没有设置代理的情况下;在简书上看到被人给的方案是离线构建;解决办法是:
下载webpack到本地下载地址：https://github.com/vuejs-templates
然后解压，把文件拷贝到你电脑的.vue-templates所在的目录--例如这是我的.vue-templates目录：C:\Users\Administrator\.vue-templates
然后构建你的vue项目：
vue init webpack your-ProjectName --offline
cd your-ProjectName
npm install/cnpm install
npm run dev

注意：webpack如何引入css文件
在webpack中，本身就有一个css-loader,所以不需要重新去下一个css-loader,只需要下载一个style-loader即可,下载style-loader的方法是在命令行中,在你所创建的项目目录下,
npm/cnpm install style-loader --save-dev,之后在你的项目里打开build/webpack.base.conf.js文件中,在module的rules那里,加入关于css规则的代码:
{
    test:'/\.css$/',
    loader:'style-loader!css-loader',
}
之后在App.vue文件中在style标签项目写入你想要引入的样式：
<style>
    #app{background-color:#fff}
</style>

(在webpack中即使不下载style-loader，不在webpack.base.conf.js中配置我上面说的内容也可以通过最后一个操作轻轻松松的引入css样式)
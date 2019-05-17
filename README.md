# node  


## 学习node第一天  

- npm 基本命令  
   +  --global (全局安装，当前在那个目录都可以)  缩写 -g
   + npm install  filename (安装filename)  filename：文件名  
   + npm i filename  效果与上一条相等  i 是 install 的缩写  
   + npm unstall filename

## 学习node第二天  

- 了解路径问题 
   +  "/"表示当前文件根目录  
   +  "./"表示在同一目录下  
   +  "../"表示上一级目录  
- 插件express  
   +  `app.use('/node_modules',express.static('./node_modules/'))` 开放资源资源 设置静态API  
   +  当express使用art-template时需要装express-art-template和art-template 前者依赖后者 
- 插件art-template 
   + 模版引擎  
- 核心模块`fs`  
   + `fs.readFile('./db.json',"utf8",function(err,data){})` 读取文件的时候是二进制形式，可以通过第二个参数utf8 ，告诉她弄成我们可以看懂的        字符    串或者data.toString()  
    
## 学习node第三天  

- 模块化  
   + 每个文件处理单独的内容，类似html,css,js,内容,样式,行为 相分离  
- callback  
   + 写的不多需要多写，多理解
   + 可以通过ajax的异步请求帮助理解  
- bootstrap  
   + 模版基本都有，可以复制copy  
- package-lock  
   + 下载时不会出现提高版本等级的现象，重下插件更加快。  
   
## 学习node第四天  

- mongoose  
   + 基本配置  
   ```javascript
   //引包
   var mongoose = require('mongoose')
   var Schema = mongoose.Schema
   //{ useNewUrlParser: true } 这个不能少
   mongoose.connect('mongodb://127.0.0.1:27017/itcast',{ useNewUrlParser: true })
   //限制类型 
   var userSchema = new Schema({
    name : String,
    age : Number,
    face : String
    })
    var User = mongoose.model("User",userSchema)
    var admin = new User({
    name : "ying",
    age: 1
    })
    //保存
    admin.save(function(err,data){
    console.log(data)
    })  
   ```   
- Promise  
   + Http-server & json-server  
   + art-template  
   + jquery  jquery有Promise的类似方法  
   ```javascript 
   //下面是jquery方法
   var data = {}
        $.get('http://127.0.0.1:3000/user/4')
            .then(function (user) {
                data.user = user
                return $.get('http://127.0.0.1:3000/jobs') //返回的值由下方76行jobs接受
            })
            .then(function (jobs) {
                data.jobs = jobs
                var htmlStr = template('tpl', data)
                //   console.log(htmlStr)
                document.querySelector('#user_form').innerHTML = htmlStr
                console.log('a')

            })  
   ```    
## 学习node第五天  

- path模块  
  + __dirname 和 __filename
  + **动态的** 获取当前文件或者文件所处目录的绝对路径
  + 用来解决文件操作路劲的相对路径问题
  + 因为在文件操作中，相对路径相对于执行 `node` 命令所处的目录
  + 所以为了尽量避免这个问题，都建议文件操作的相对路劲都转为：**动态的绝对路径**
  + 方式：`path.join(__dirname, '文件名')` 避免手动添加路径时的小问题


   

  


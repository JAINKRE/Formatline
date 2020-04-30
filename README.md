# 剑客科技 代码一行格式化工具

---

**访问在线版: https://d.jeiku.net/web/Formatline.html (基于我司服务器.可快速访问)**



## V1.00版本

* 使用vue架构 和 javascript 开发
* 实现代码格式化
* 实现动态字数统计
* 匹配浏览器
* 实现格式化代码复制
* 上传Github
* 开源许可 MIT

---

## 用途:

用于将多行代码合并到一行的情景中,如下所示:  

> 以下为该工具的初代设计代码,工具基于vue框架

```html
<!--苏州市剑客电子科技有限公司，代码一行格式化 在线版本-->
<!DOCTYPE html>
<html lang="zh-cmn">
<head >
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <meta name="author" content="SuZhou JEIKU Electronic Technology Co.,Ltd." /> 
  <meta name="robots" content="all" /> 
  <meta name="keywords" content="代码一行格式化 一个将多行代码格式化成一行的在线工具" /> 
  <meta name="description" content="一个将多行代码格式化成一行的在线工具" /> 
  <title>剑客科技 代码一行格式化工具</title>
  <style>
    body{
      background-color: #192125;
      color: white;
      font-family: 微软雅黑;
    }
    .button{
      background-color: #263238;
      border: 0ch;
      border-radius: 3px;
      color: aliceblue;
      cursor:pointer;
    }
    .textsreas{
      background-color: #181f22;
      margin-top: 10px;
      width: 100%;
      height: 666px;
      color: aliceblue;
      margin-bottom: 25px;
    }
    .hrefs{
      text-decoration:none;
      color: dodgerblue;
    }
    .left{
      margin-left: 10px;
    }
  </style>
</head>
<body style="min-width:600px;">
  <div style="
    font-size: 32px;
    text-align: center;
    margin-bottom: 20px;
    margin-top: 30px;
  ">剑客科技 代码一行格式化工具</div>
  <div id="app" style="margin-left: 100px;margin-right: 100px;">
    <button class="button" @click=clear>清除</button>
    <button  class="button" style="margin-left: 10xp;" @click='copytextob'>复制格式化代码</button>
    <a style="margin-left: 20px;">当前输入字数 : {{this.message.length}}个字</a>
    <input type="text" style="width: 100%;text-align: left;line-height: 10px;text-indent: 5px;margin-top: 15px;" v-model="message"  placeholder="把需要格式化的代码输入到这里">
    <textarea readonly="readonly" class="textsreas" style=" word-wrap: break-word;" id="textobjects" >{{message}}</textarea>
    <div style="font-size: 12px;text-align: center;">
      <a class="hrefs" href="http://www.jeiku.net" target="_blank">苏州剑客电子科技有限公司</a>
      <a class="hrefs left" href="https://github.com/JEIKU-Technology/Formatline/blob/master/LICENSE" target="_blank">开源许可:MIT</a>
      <a class="hrefs left" href="http://www.github.com/jeiku-technology" target="_blank">GitHub: Jeiku-Technology</a>
      <a class="hrefs left" href="https://d.jeiku.net/web/Formatline.html" target="_blank">在线版本</a>
    </div>
    <hr>
    <a>{{outs}}</a>
    <a style=" word-wrap: break-word;">{{message}}</a>
  </div>
  <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.js"></script>
  <script>
    const app = new Vue({
      el:"#app",
      data:{
        message:"",
        textnum:0,
      },
      methods: {
        clear(){
          if (this.message.length == 0){
          }else{
          alert("成功删除"+this.message.length+"个字符!输入框已清空!!");
          this.message = ""
          }
        },
        copytextob(){
          if (this.message.length == 0){
            alert("输入框没有输入任何内容哦!无法复制格式化代码");
          }else{
          var textob=document.getElementById("textobjects");
          textob.select();
          document.execCommand("Copy");
            alert("已复制到剪贴板中！一共"+this.message.length+"个字符!");
          }
        },
      },
    })
  </script>
</body>
</html>
```

* 将上述代码通过工具可以格式化如下:

> 通过复制按钮复制 该格式化包含空格

```html
<!--苏州市剑客电子科技有限公司，代码一行格式化 在线版本--> <!DOCTYPE html> <html lang="zh-cmn"> <head >   <meta charset="UTF-8">   <meta name="viewport" content="width=device-width, initial-scale=1.0">   <meta http-equiv="X-UA-Compatible" content="ie=edge">   <meta name="author" content="SuZhou JEIKU Electronic Technology Co.,Ltd." />    <meta name="robots" content="all" />    <meta name="keywords" content="代码一行格式化 一个将多行代码格式化成一行的在线工具" />    <meta name="description" content="一个将多行代码格式化成一行的在线工具" />    <title>剑客科技 代码一行格式化工具</title>   <style>     body{       background-color: #192125;       color: white;       font-family: 微软雅黑;     }     .button{       background-color: #263238;       border: 0ch;       border-radius: 3px;       color: aliceblue;       cursor:pointer;     }     .textsreas{       background-color: #181f22;       margin-top: 10px;       width: 100%;       height: 666px;       color: aliceblue;       margin-bottom: 25px;     }     .hrefs{       text-decoration:none;       color: dodgerblue;     }     .left{       margin-left: 10px;     }   </style> </head> <body style="min-width:600px;">   <div style="     font-size: 32px;     text-align: center;     margin-bottom: 20px;     margin-top: 30px;   ">剑客科技 代码一行格式化工具</div>   <div id="app" style="margin-left: 100px;margin-right: 100px;">     <button class="button" @click=clear>清除</button>     <button  class="button" style="margin-left: 10xp;" @click='copytextob'>复制格式化代码</button>     <a style="margin-left: 20px;">当前输入字数 : {{this.message.length}}个字</a>     <input type="text" style="width: 100%;text-align: left;line-height: 10px;text-indent: 5px;margin-top: 15px;" v-model="message"  placeholder="把需要格式化的代码输入到这里">     <textarea readonly="readonly" class="textsreas" style=" word-wrap: break-word;" id="textobjects" >{{message}}</textarea>     <div style="font-size: 12px;text-align: center;">       <a class="hrefs" href="http://www.jeiku.net" target="_blank">苏州剑客电子科技有限公司</a>       <a class="hrefs left" href="https://github.com/JEIKU-Technology/Formatline/blob/master/LICENSE" target="_blank">开源许可:MIT</a>       <a class="hrefs left" href="http://www.github.com/jeiku-technology" target="_blank">GitHub: Jeiku-Technology</a>       <a class="hrefs left" href="https://d.jeiku.net/web/Formatline.html" target="_blank">在线版本</a>     </div>     <hr>     <a>{{outs}}</a>     <a style=" word-wrap: break-word;">{{message}}</a>   </div>   <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.js"></script>   <script>     const app = new Vue({       el:"#app",       data:{         message:"",         textnum:0,       },       methods: {         clear(){           if (this.message.length == 0){           }else{           alert("成功删除"+this.message.length+"个字符!输入框已清空!!");           this.message = ""           }         },         copytextob(){           if (this.message.length == 0){             alert("输入框没有输入任何内容哦!无法复制格式化代码");           }else{           var textob=document.getElementById("textobjects");           textob.select();           document.execCommand("Copy");             alert("已复制到剪贴板中！一共"+this.message.length+"个字符!");           }         },       },     })   </script> </body> </html>
```

* 手动复制页面代码

> 该格式化只有最大一个空格

```html
<!--苏州市剑客电子科技有限公司，代码一行格式化 在线版本--> <!DOCTYPE html> <html lang="zh-cmn"> <head > <meta charset="UTF-8"> <meta name="viewport" content="width=device-width, initial-scale=1.0"> <meta http-equiv="X-UA-Compatible" content="ie=edge"> <meta name="author" content="SuZhou JEIKU Electronic Technology Co.,Ltd." /> <meta name="robots" content="all" /> <meta name="keywords" content="代码一行格式化 一个将多行代码格式化成一行的在线工具" /> <meta name="description" content="一个将多行代码格式化成一行的在线工具" /> <title>剑客科技 代码一行格式化工具</title> <style> body{ background-color: #192125; color: white; font-family: 微软雅黑; } .button{ background-color: #263238; border: 0ch; border-radius: 3px; color: aliceblue; cursor:pointer; } .textsreas{ background-color: #181f22; margin-top: 10px; width: 100%; height: 666px; color: aliceblue; margin-bottom: 25px; } .hrefs{ text-decoration:none; color: dodgerblue; } .left{ margin-left: 10px; } </style> </head> <body style="min-width:600px;"> <div style=" font-size: 32px; text-align: center; margin-bottom: 20px; margin-top: 30px; ">剑客科技 代码一行格式化工具</div> <div id="app" style="margin-left: 100px;margin-right: 100px;"> <button class="button" @click=clear>清除</button> <button class="button" style="margin-left: 10xp;" @click='copytextob'>复制格式化代码</button> <a style="margin-left: 20px;">当前输入字数 : {{this.message.length}}个字</a> <input type="text" style="width: 100%;text-align: left;line-height: 10px;text-indent: 5px;margin-top: 15px;" v-model="message" placeholder="把需要格式化的代码输入到这里"> <textarea readonly="readonly" class="textsreas" style=" word-wrap: break-word;" id="textobjects" >{{message}}</textarea> <div style="font-size: 12px;text-align: center;"> <a class="hrefs" href="http://www.jeiku.net" target="_blank">苏州剑客电子科技有限公司</a> <a class="hrefs left" href="https://github.com/JEIKU-Technology/Formatline/blob/master/LICENSE" target="_blank">开源许可:MIT</a> <a class="hrefs left" href="http://www.github.com/jeiku-technology" target="_blank">GitHub: Jeiku-Technology</a> <a class="hrefs left" href="https://d.jeiku.net/web/Formatline.html" target="_blank">在线版本</a> </div> <hr> <a>{{outs}}</a> <a style=" word-wrap: break-word;">{{message}}</a> </div> <script src="https://cdn.jsdelivr.net/npm/vue@2.6.10/dist/vue.js"></script> <script> const app = new Vue({ el:"#app", data:{ message:"", textnum:0, }, methods: { clear(){ if (this.message.length == 0){ }else{ alert("成功删除"+this.message.length+"个字符!输入框已清空!!"); this.message = "" } }, copytextob(){ if (this.message.length == 0){ alert("输入框没有输入任何内容哦!无法复制格式化代码"); }else{ var textob=document.getElementById("textobjects"); textob.select(); document.execCommand("Copy"); alert("已复制到剪贴板中！一共"+this.message.length+"个字符!"); } }, }, }) </script> </body> </html>
```

## 开源许可:MIT许可

### 许可证:  https://github.com/JEIKU-Technology/Formatline/blob/master/LICENSE

```
MIT License

Copyright (c) 2020 剑客科技

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```


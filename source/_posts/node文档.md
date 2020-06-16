---
title: node文档
date: 2020-06-16 15:28:56
tags:
---

# node文档
## 处理有文件的表单
[nodeformidable 官方文档](https://github.com/node-formidable/formidable)

### form提交方式
如果在form表单提交时有文件上传那么需要在form中加enctype=“multipart/form-data” 方式必须是post

```html
<form  id="form1" name="myForm" action="" method="post" enctype="multipart/form-data">
```
### jquery处理
```js
$("#form1").submit(function (event) {
         event.preventDefault();
         $.ajax({
             url:"/user/register",
             type:"POST",
             data:new FormData(this),
             contentType:false,
             processData:false,
             success:function(status){
                 console.log(status);
             }
         })
     })
```
### 引用formidable
```js
const Formidable = require('formidable');
const util = require('util');
const form = new Formidable();
form.uploadDir = "/my/dir";//上传路径
form.keepExtensions = true;//扩展名
form.parse(req, (err, fields, files) => {
  res.writeHead(200, { 'content-type': 'text/plain' });
  res.write('received upload:\n\n');
  res.end(util.inspect({ fields: fields, files: files }));
});
```
### 结果示例
```json
received upload:  

{ fields: { title: 'title的内容' },  
  files:      //所有type="file"类型的数据对象  
   { upload:   
      { domain: null,  
        _events: {},  
        _maxListeners: 10,  
        size: 41966,             //文件大小  
        path: '/my/dir/upload_ecbf965abc1e14c2ffc86875c2f5eaa8.jpg',   //文件保存路径  
        name: 'avatar.jpg',     //上传前的文件名  
        type: 'image/jpeg',    //文件类型  
        hash: null,  
        lastModifiedDate: Sat May 16 2015 10:38:57 GMT+0800 (CST),  
        _writeStream: [Object] 
        }
    } 
}  
```
vue的关于姓名文字，电话号码，身份证号码的打码隐藏的过滤器

1.关于姓名文字的打码显示

```js
formatName (value) {
      if (!value) return '';
      let str = value;
      if(str.length == 2){
        str = str.toString().replace(/^([^\x00-\xff])([^\x00-\xff]{0,})([^\x00-\xff])/g , '$1*')
      }else if(str.length == 3){
        str = str.toString().replace(/^([^\x00-\xff])([^\x00-\xff]{0,})([^\x00-\xff])/g , '$1*$3')
      }else if(str.length == 4){
        str = str.toString().replace(/^([^\x00-\xff])([^\x00-\xff]{0,2})([^\x00-\xff])/g , '$1**$3')
      }else if(str.length > 4){
        str = str.toString().replace(/^([^\x00-\xff])([^\x00-\xff]{0,3})([^\x00-\xff])/g , '$1***$3')
      }else{}
      // str = str.toString().replace(/^([^\x00-\xff])([^\x00-\xff]{1,3})([^\x00-\xff])/g , '$1**$3')
      return str;
    }
```

2.电话号码打码显示

```js
formatPhone (value) {
  if (!value) return '';
  let str = value;
  str = str.toString().replace(/^(\d{3})(\d{4})(\d{4})/g , '$1****$3')
  return str;
})
```

3.身份证号码的打码

```js
formatIDcard (value) {
  if (!value) return '';
  let str = value;
  str = str.toString().replace(/^(.{6})(?:\w+)(.{4})$/ , '$1********$2')
  return str;
})
```

4.

```js
 hidden : function(str,frontLen,endLen) {    //str：要进行隐藏的变量  frontLen: 前面需要保留几位    endLen: 后面需要保留几位
		         var len = str.length-frontLen-endLen;
		         var xing = '';
		         for (var i=0;i<len;i++) {
		         xing+='*';
		        }
		         return str.substring(0,frontLen)+xing+str.substring(str.length-endLen);
		   }
       
       }
```


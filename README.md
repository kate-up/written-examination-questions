# draw lessons from the past 
##### Record own growth,after all,people who like excellent people also like excellent people
[title](URL)
**Bold加粗**
*斜体*
==高亮==

段落：段落之间空一行

换行符：一行结束时输入两个空格  
*列表：*添加星号成为一个新的列表项  
引用： >引用内容  
内嵌代码：`alert('Hello World')`  
画水平线（HR）：---------  
方框：-[警方说你哦]-  ![链接]()  

## 图片  
使用Markdown将图像插入文章，你需要在Markdown编辑器输入 ![]() 。 这时在预览面板中会自动创建一个图像上传框。你可以从电脑桌面拖放图片(.png, .gif, .jpg)到上传框, 或者点击图片上传框使用标准的图像上传方式。 如果你想通过链接插入网络上已经存在的图片，只要单击图片上传框的左下角的“链接”图标，这时就会呈现图像URL的输入框。想给图片添加一个标题, 你需要做的是将标题文本插图中的方括号，e.g;![This is a title]().
## 脚注
脚注不存在于标准Markdown中。
使用这样的占位符号可以将脚注添加到文本中:[^1]. 另外，你可以使用“n”而不是数字的[^n]所以你可以不必担心使用哪个号码。在您的文章的结尾，你可以如下图所示定义匹配的注脚，URL将变成链接:  

这里是脚注[^1]
[^1]: 这里是脚注的内容
 
这里是脚注[^n]
[^n]: 这里是脚注的内容
## 写代码  
添加内嵌代码可以使用一对回勾号 `alert('Hello World')`.对于插入代码, Ghost支持标准的Markdown代码和GitHub Flavored Markdown (GFM) [4]  。标准Markdown基于缩进代码行或者4个空格位:

   <header>    
   <h1>{{title}}</h1>
   </header>
GFM 使用三个回勾号  
<header>
    <h1>{{title}}</h1>
</header>
  
## 链接

This is a paragraph that contains a [link to example]()  
## 列表格式

This paragraph contains a list of items.
 
* Item 1
 
* Item 2
 
* Item three  
使用Markdown 引用文本：  

This paragraph has a quote
 
> That is pulled out like this
from the text my post.

## 统计一个字符串中字符出现的次数
###### 获得次数最多的一个，共出现几次???
`   <script>  

    var str = "HelloWorld";   
 
    var dict = [];   //用字典的方式定义空的对象  
 
    for(var i=0; i<str.length; i++){   //遍历字符串中每个字符
 
      if(dict[str[i]] === undefined){     //如果dict对象中不包含当前字母为属性名的成员
   
         dict[str[i]] = 1;                //将强行添加一个当前字母为属性名  初始化为1
     
       }else{
   
         dict[str[i]] += 1;             //否则就是出现过该字母  在属性值的基础之上 +1
     
       }
      
     }
     console.log(dict);
     //利用奥运会跳水比赛记分牌的方式  最大值都会覆盖前面小的值  
     var max, count = 0;              //初始化值
     for(var key in dict){            // 遍历对象dict中每个属性
       if(dict[key] > count){        //属性的属性值 大于 count 的话 
         max = key;
         count = dict[key];
       }
     }
     console.log(max, count);  
 </script>`  

## 数组去重？？？
`<script>

    var arr = ['a','b','c','d','a','b']; 
    
    var dict = {};                           //先定义一个空的对象（字典）
    
    for(var i = 0; i < arr.length; i++){  
    
        dict[arr[i]] = 0;                //遍历arr数组 将遍历到的属性值放在dict对象中  已经遍历过的会将前面的覆盖
        
    }
    
    console.log(dict);  
    
    var result = [];          //将结果存放在数组中  
    
    var i = 0;
    
    for( result[i++] in dict);
    
    console.log(result);
    
</script>`

## 深拷贝
`<script>    
  
      var lilei = {   
     
         sname:"Li Lei",  
        
         age:12,  
        
        score:null,  
        
        address:{  
        
            city:"北京",  
            
            area:"海淀",  
            
            street:"万寿路"  
            
        },  
        
        friends:["jack","rose","lucy"]  
        
     }  
     
     function clone(obj){  
     
         if(obj === null){         //null  
         
             return null  
             
         }  
         
         if( {}.toString.call(obj) === "[Object Array]" ){    //数组  
         
            var newArr = [];  
            
            newArr = obj.slice();  
            
            return newArr;  
            
         }  
         
         var newObj = {};  
         
         for( var key in obj ){  
         
             if( typeof obj[key] !== object ){        //原始类型  
             
                 newObj[key] = obj[key];  
                 
             }else{  
             
                 newObj[key] = clone( obj[key] )       //对象  
                 
             }  
              
         }  
         
     }  
     
  </script>`

## null和undefined的区别
>undefined是访问一个未被初始化的变量返回的值  
null是访问一个上不存在的对象时返回的值

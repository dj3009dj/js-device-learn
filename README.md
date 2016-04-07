# js-device-learn
js中常见的全局写法是：
window.device=(function(JsBridge){...var log=function(value){...}...})(window.JsBridge);
此时就可以直接使用device.log(value)去调用了。即：
首先使用self-invoking函数自执行，然后使用device表示这个全局函数
再使用device.log去调用log子函数
###############################################################################################
js中常见的定义数组的方式是：
var List=['log','checkApi'];
对比java中定义数组的方式：
string Str[]={"log","checkApi"};
##################################################################################################
js中常见的定义对象的方式是:
var Api={
'p1':'log',
'p2':'check'
};
由于js中所有的键名都是字符串，所以不加引号也是可以的,上述可以写成
var Api={
p1:'log',
p2:'check'
}
####################################################################################################
for...in格式
var check=function(apiName,apiMap){
for(var k in apiMap)
{apiMap[k].indexOf(apiName)>-1
}
}
其中k表示在数组apiMap中的索引号，观察它是否包含apiName
#####################################
第一部分的观察就到这里了。
JSON.stringify：将Javascript值转化成JSON对象
JSON.stringify([]);//'[]'
JSON.stringify('foo');//'"foo"'
JSON.strngify(['true',2,false]);//'["true",2,false]'
JSON.stringify({x:5});//'{"x":5}'

JSON.parse:解析JSON对象成Javascript值
JSON.parse('[]');//[]
JSON.parse('"foo"');//'foo'
JSON.parse('["true",2,false]');//['true',2,false]


#QueryList交流QQ群:123266961 <a target="_blank" href="http://shang.qq.com/wpa/qunwpa?idkey=a1b248ae30b3f711bdab4f799df839300dc7fed54331177035efa0513da027f6"><img border="0" src="http://pub.idqqimg.com/wpa/images/group.png" alt="╰☆邪恶 魔方☆" title="╰☆邪恶 魔方☆"></a>

#QueryList简介
***
QueryList是一个基于phpQuery的通用列表采集类,是一个简单、 灵活、强大的采集工具，采集任何复杂的页面     基本上就一句话就能搞定了。

#QueryList 使用
```php
//实例化一个采集对象
$hj = new QueryList('http://www.baidu.com/s?wd=jaekj',array('title'=>array('h3','text')));
//输出结果：二维关联数组
print_r($hj->jsonArr);
//输出结果：JSON数据
echo $hj->getJSON();
```
上面的代码实现的功能是采集百度搜索结果页面的所有搜索结果的标题,然后分别以数组和JSON格式输出。
###QueryList 构造函数原型：
>***QueryList***($page,$regArr,$regRange='',$getHtmlWay="curl",$output_encoding=false)

一共有五个参数，后面三个参数是可选的

* *$page*            要抓取的网页URL地址(默认支持https);或者是html源代码

* *$regArr*         【选择器数组】说明：格式array("名称"=>array("选择器","类型"),.......),【类型】说明：值 "text" ,"html" ,"属性"

* *$regRange*       【块选择器】：指 先按照规则 选出 几个大块 ，然后再分别再在块里面 进行相关的选择

* *$getHtmlWay*     【源码获取方式】指是通过curl抓取源码，还是通过file\_get_contents抓取源码,当$page参数为URL时此参数才有效

* *$output_encoding*【输出编码格式】指要以什么编码输出(UTF-8,GB2312,.....)，防止出现乱码,如果设置为 假值 则不改变原字符串编码

###QueryList 属性
* **得到多维数组格式的采集结果**

	>***jsonArr***

###QueryList 方法
*  **重新设置选择器**

	>void ***setQuery***($regArr,$regRange='')

	一共两个参数,第二个参数是可选的，参数意义同构造函数。

* **得到JSON格式的采集结果**

	> string ***getJSON***()

	无参，返回JSON字符串。

##QueryList 依赖库
```
phpQuery
```

phpQuery项目主页:[https://code.google.com/p/phpquery/](https://code.google.com/p/phpquery/)

##其它说明
QueryList 内置的只是简单的源码抓取方法，遇到更复杂的抓取情况，如：需要登陆
身份验证 时，请配合其它的PHP的HTTP类来使用，通过将辅助的HTTP类抓取到的网页源码传给QueryList即可。
##DEMO站
微动态:[http://querylist.jaekj.com/](http://querylist.jaekj.com/)

* thinkphp版本:V3.1.2
* QueryList版本:V1.6
* 后台地址: /admin
* 后台账号密码: guest guest

这个demo站实现的功能相当于一个轻量级的微博站，内容全自动采集更新，可以自定义时间间隔采集任意站点的信息，自动更新到这个站点来，只需要在后台规则库简单的添加一条规则就可以实现全自动采集了，大家可以自行进入后台进行尝试，体验QueryList的魅力！
##作者信息
```
Author : Jaeger
Email : hj.q@qq.com
交流QQ群:123266961 
```













UEditor-yiiv1.x-ext
===================

Yii v1.x 的Ueditor扩展，支持的UEditor版本为1.4.3。<br>
支持自动的缩略图管理。<br>
支持水印。<br>
使用TP框架的tpImage来生成和处理图片。

###配置说明
---------------------
<ul>
<li>
1、将ueditor放在项目的/protected/extensions/目录下。
</li>
<li>
2、在config.php中配置controllerMap，来指定ueditor的访问路径
```php
'controllerMap'=>array(
    'ueditor'=>array(
        'class'=>'ext.ueditor.UeditorController',
    ),
),
```
	可选配置：
```php
'controllerMap'=>array(
    'ueditor'=>array(
        'class'=>'ext.ueditor.UeditorController',
        'config'=>array(),//参考config.json的配置，此处的配置具备最高优先级
        'thumbnail'=>true,//是否开启缩略图
        'watermark'=>'',//水印图片的地址，使用相对路径
        'locate'=>9,//水印位置，1-9，默认为9在右下角
    ),
),
```
</li>
<li>
3、在view中使用widget。
    在原有的view中添加即可，注意id填写为原有的textarea的id。
    注意，使用这个widget时，不要删除原有的代码，只要添加此处的代码即可。
```php
$this->widget('ext.ueditor.UeditorWidget',
        array(
                'id'=>'Post_content',//页面中输入框（或其他初始化容器）的ID
                'name'=>'editor',//指定ueditor实例的名称,个页面有多个ueditor实例时使用
        )
);
```
</li>
<li>
4、错误排除<br>
出现错误请查看上传目录的权限问题。默认上次到根目录的upload/目录。<br>
不要开启Yii的调试，因为UEditor的返回都是json格式，开启调试会导致返回格式不识别。
</li>
其他说明
---------------------
1、原1.3.6版本插件<br>
因为1.3.6版本作为一个比较稳定的版本，还是保留下载地址。<br>
下载地址：http://www.crazydb.com/upload/file/20140531/7384_yii-ext-ueditor136.tar.gz<br>
参考：http://www.crazydb.com/archive/百度编辑器UEditor的Yii扩展<br>

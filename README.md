# epub_reader online
越来越多的书籍以epub格式提供，实现了一个简单的在线epub格式阅读器, 该功能采用iframe方式以类似组件的方式提供。

# 特性
- 图片懒加载
- 目录
- 上一页
- 下一页

# 使用
```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title></title>
	<script type="text/javascript">

function onloadframe(self) {
    window.ViewContainer = self.contentWindow;
}

function load(self)
{
	window.ViewContainer.load(self.files[0]);
}

	</script>
</head>
<body>
	<input type="file" id="file" onchange="load(this)">
	<div id="container">
		
	</div>
	<iframe src="./index.html" id="frame" style="width:100%;height: 100vh;" onload="onloadframe(this)"/>
</body>
</html>

```
# API
- load(file) 加载文件
- next_page(offset) 翻页

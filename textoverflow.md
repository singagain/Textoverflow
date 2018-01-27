
### 兼容所有浏览器的多行文字超出显示省略号
.home_news_text为 p 标签的子容器，必须定义高度
```javascript
									$(".home_news_text").each(function(i){
										var aHeight =  $(this).height()
										var $p = $("p", $(this)).eq(0);
										while ($p.outerHeight() > aHeight) {
											$p.text($p.text().replace(/(\s)*([a-zA-Z0-9]+|\W)(\.\.\.)?$/, "..."));
										
```
### 兼容webkit内核的多行超出显示省略号
注：多数手机浏览器支持，华为浏览器除外
```css
	 overflow: hidden; 
     text-overflow: ellipsis;
   	 display: -webkit-box;
    	-webkit-line-clamp: 2;
    	-webkit-box-orient: vertical; 
```

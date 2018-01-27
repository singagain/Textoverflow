### 表格数据刷新时排序的实例


定义变量reseFall，latestPrice用来记录按钮状态，
0时不排序 
1时向上排序 
2时向下排序 

thIndex用来记录当前是那种排序

sortName 用来记录排序的字段是什么

```javascript
seajs.use('module_market',function(bill){							
				var	reseFall = 0;
				var latestPrice = 0
			$(".latest_price").click(function () {
				reseFall = 0;
				latestPrice = latestPrice + 1;
				$(".rise_fall").css("background", "#fff")
				$(this).css("background", "#F8F8F8");
				$(".rise_fall").find("i").css("background-position", "0 0");
				if (latestPrice == 0) {
					$(this).find("i").css("background-position", "0 0");
					bill.clickNum = 0;
					bill.thIndex=3;
					bill.sortName = "price"
				} else if (latestPrice == 1) {
					$(this).find("i").css("background-position", "-8px 0");
					bill.clickNum = 1;
					bill.thIndex=3;
					bill.getMarket();
					bill.sortName = "price"
				} else if (latestPrice == 2) {
					$(this).find("i").css("background-position", "-23px 0");
					bill.clickNum = 2;
					bill.thIndex=3;
					bill.getMarket();
					latestPrice = 0;
					bill.sortName = "price"
				}

			})

				$(".rise_fall").click(function () {
					latestPrice = 0;
					reseFall = reseFall + 1;
					$(".latest_price").css("background", "#fff");
					$(".latest_price").find("i").css("background-position", "0 0");
					$(this).css("background", "#F8F8F8");
					if (reseFall == 0) {
						$(this).find("i").css("background-position", "0 0");
						bill.clickNum = 0;
						bill.thIndex=3;
						bill.sortName = "rangeOf24h"
					} else if (reseFall == 1) {
						$(this).find("i").css("background-position", "-8px 0");
						bill.clickNum = 1;
						bill.thIndex=3;
						bill.getMarket();
						bill.sortName = "rangeOf24h"
					} else if (reseFall == 2) {
						$(this).find("i").css("background-position", "-23px 0");
						bill.clickNum = 2;
						bill.thIndex=3;
						bill.getMarket();
						bill.sortName = "rangeOf24h"
						reseFall = 0;
						
					}
				})
				
			});
```
### 



define(function (require, exports, module) {
}



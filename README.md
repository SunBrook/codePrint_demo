# codePrint_demo
条形码生成与打印，二维码生成与打印



> 条形码 JsBarcode：https://github.com/lindell/JsBarcode
>
> 二维码 qrCode：https://github.com/davidshimjs/qrcodejs



## 条形码展示

1. 首先，创建一个 `<svg> ` 或者 `<canvas>` 或者 `<img>`
2. 生成条形码

```javascript
<!--官方示例-->

<svg id="barcode"></svg>
<!-- or -->
<canvas id="barcode"></canvas>
<!-- or -->
<img id="barcode"/>

JsBarcode("#barcode", "Hi!");
// or with jQuery
$("#barcode").JsBarcode("Hi!");   
```





## 二维码展示

1. 声明一个div 
2. 生成二维码

```javascript
<!--官方示例-->
    
<div id="qrcode"></div>

var qrcode = new QRCode(document.getElementById("qrcode"), {
	text: "http://jindo.dev.naver.com/collie",
	width: 128,
	height: 128,
	colorDark : "#000000",
	colorLight : "#ffffff",
	correctLevel : QRCode.CorrectLevel.H
});
```





## 调用浏览器打印

- 调用函数 `window.print()`
- `page-break-after` 设置在表格元素之后始终进行分页的分页行为，用 always 强制放上分页符。

```html
<!--页面元素-->

<div>
	<p>起点：上海</p>
    <p>终点：广州</p>
    <p>条码：15790025100</p>
</div>
<div style="page-break-after:always"></div>
<div>
	<p>起点：北京</p>
    <p>终点：深圳</p>
    <p>条码：15790025101</p>
</div>

<script>
setTimeout(function () {
        window.print();	//打印
        location.reload(); //页面刷新
    }, 500);
</script>

```


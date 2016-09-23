### loading组件

`loading`组件，具有`pageloading`和`iconloading`两种样式。

在html文件中引入对应的css和js

``` html

<link rel="stylesheet" href="widget/loading/loading.css">

<script src="widget/loading/loading.js"></script>

```

js文件中调用：

```js

$.ajax({
        url: url,
        type: 'POST',
        data: sendData,
        beforeSend: function () {

        	//页面loading, 不能再进行其他操作，适合比如提交按钮
            lnv.pageloading();

        }
    })
    .done(function (res) {

    })
    .fail(function (jqXHR, textStatus, errorThrown) {

    })
    .always(function () {

		//在这里删除页面loading
        lnv.destroyloading();

    });

```

效果如下：

![loading](img/loading.png)

js文件中调用：

```js

$.ajax({
        url: url,
        type: 'POST',
        data: sendData,
        beforeSend: function () {

        	//按钮内调用，需要传入按钮的jquery对象
            lnv.iconloading("#submit_btn");

        }
    })
    .done(function (res) {

    })
    .fail(function (jqXHR, textStatus, errorThrown) {

    })
    .always(function () {

		//在这里删除按钮loading
        lnv.destroyloading("#submit_btn");

    });


```

效果如下：

![loading2](img/loading2.png)
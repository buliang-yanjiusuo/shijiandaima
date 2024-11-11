# 告诉你怎么给静态网页添加时间

要在静态网页上添加时间显示，可以通过JavaScript来动态更新当前时间，并使用HTML和CSS来展示它。下面是一个简单的步骤和代码示例，帮助你将实时更新时间添加到静态网页中。

### 步骤：
1. **HTML部分**：创建一个容器用于显示时间。
2. **JavaScript部分**：编写代码动态获取当前时间，并实时更新显示。
3. **CSS部分**：可以为时间展示的样式进行美化。

### 完整代码示例：

```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>网页时间显示</title>
    <style>
        /* 时间显示容器样式 */
        #clock {
            font-size: 30px;
            font-family: 'Arial', sans-serif;
            background-color: #222;
            color: white;
            padding: 10px;
            position: fixed;
            top: 10px;
            right: 10px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            text-align: center;
        }
    </style>
</head>
<body>

    <!-- 时间显示容器 -->
    <div id="clock"></div>

    <script>
        // 获取时间并格式化显示
        function updateTime() {
            const now = new Date();  // 获取当前时间
            let hours = now.getHours();  // 获取小时
            let minutes = now.getMinutes();  // 获取分钟
            let seconds = now.getSeconds();  // 获取秒数

            // 格式化为两位数
            hours = hours < 10 ? '0' + hours : hours;
            minutes = minutes < 10 ? '0' + minutes : minutes;
            seconds = seconds < 10 ? '0' + seconds : seconds;

            // 设置时间显示内容
            document.getElementById('clock').textContent = hours + ':' + minutes + ':' + seconds;
        }

        // 每秒更新时间
        setInterval(updateTime, 1000);

        // 初始化时间显示
        updateTime();
    </script>

</body>
</html>
```

### 代码说明：
1. **HTML部分**：
   - 使用一个`<div>`元素来显示时间，`id="clock"`用来标识这个时间显示区域。

2. **CSS部分**：
   - 设置了时间显示区域的样式，例如：背景色为深色（黑色），文字颜色为白色，居中显示，固定在页面的右上角。
   - `box-shadow`和`border-radius`使其看起来更有层次感和圆角效果。

3. **JavaScript部分**：
   - `updateTime`函数获取当前时间并格式化为`HH:MM:SS`的格式。
   - 使用`setInterval`每秒钟调用一次`updateTime`函数，确保时间实时更新。
   - 页面加载时，立即调用`updateTime`函数初始化显示时间。

### 解释：
- **`Date()`**：JavaScript的`Date`对象用于获取当前的日期和时间。
- **`setInterval()`**：用来设置一个定时器，每秒（1000毫秒）更新一次页面上的时间。
- **`padStart()`**：为了确保小时、分钟和秒数都为两位数，如果值小于10，则在前面补充0。

这样，当前时间将会实时显示在页面的右上角，并每秒自动更新。如果需要调整位置或样式，可以修改CSS部分。

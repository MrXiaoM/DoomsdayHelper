# 末日社团公开API

这个文档会写出 `公开的API` 用法

~~虽然我觉得除了管理没人会用~~

## 玩家信息

* 请求URL: [`api.doomteam.fun/player`](https://api.doomteam.fun/player)
* 方法: `GET`
* 必要字段: `player=[玩家名称]`
* 示例: [`api.doomteam.fun/player?player=CuteStarX`](https://api.doomteam.fun/player?player=CuteStarX)
* 成功返回示例: 


```json
{"success":true,"data":{"username":"CuteStarX","firstPlayed":1613223084471,"lastPlayed":1630412541060,"money":695.65,"status":"离线","id":"6c803ada-1171-3fdb-b0a6-8fccb3f39888","kits":{"comp":1},"parkours":{"level-2":6,"level-3":0,"level-1":0},"is-cursed":false,"is-muted":false,"remaining_second":419,"needles":10,"tag":{"now":"&7[&a萌新&7]&e","count":0},"residences":[]}}
```
* 失败返回示例:


```json
{"success": false, "status_code": "404", "msg": "[object Object]" "readme": https://www.doomteam.fun/developer}
```

## 服务器状态

* 请求URL: [`api.doomteam.fun/status`](https://api.doomteam.fun/status)
* 方法: `GET`
* 成功示例:


```json
{"success":true,"data":{"tps":"20.0 20.0 20.0","onlinePlayers":1,"maxPlayers":32,"players":["Candle_luminary"]}}    
```

## 调用示例

~~自己找JSON解析库解析~~

### JAVA

```java
    void printJsonString() throws IOException {
        URL u = new URL("https://api.doomteam.fun/status");
        URLConnection uc = u.openConnection();
        try (InputStream in = uc.getInputStream()) {
            byte[] bytes = new byte[in.available()];
            in.read(bytes);
            String jsonString = new String(bytes);
            System.out.println(jsonString);
        }
    }
```

### .NET (CSharp)

```c#
// 最朴素的方法
String url = "https://api.doomteam.fun/status";
String text = new WebClient().DownloadString(url);
```

### JAVASCRIPT

jQuery ajax:

```javascript
$.ajax({
    url: "https://api.doomteam.fun/status"
    type: "GET",
    success: function(text){
        alert(text);
    },
    error: function(text){
        alert(text);
    }
})
```

### PHP

```php
<?php
$text=file_get_contents("https://www.doomteam.fun/status");
echo $text;
?>
```


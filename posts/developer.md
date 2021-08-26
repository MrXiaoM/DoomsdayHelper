# 末日社团 开发人员文档

这份文档会写出开发人员可能需要的东西，未来服务器可能会开放API接口，半开源到 `Github` 让玩家能够开发可操作服务器基础插件数据的插件。

## PlaceholderAPI 变量

`respawnneedle_get` 获取玩家复活针数量

`respawnneedle_get_玩家名` 获取指定玩家复活针数量

**注意，在找不到玩家指定玩家时，会创建对应名称的配置文件，请不要乱用来占用服务器内存，否则我们将关闭这个功能**

`playerpoints_points` 获取玩家点券数量

`playerpoints_points_玩家名` 获取指定玩家点券数量

别问我为什么不用官方的点券变量附属，我是傻逼，没看到有就写了个

`mypapi_party` 获取玩家的 `mcMMO` 小队名，无小队时将返回 `无团体`

`mypapi_marry` 获取玩家的结婚状态，已婚将返回 `§7[§c已婚§7]`，未婚将返回空字符串

`udtitle_title` 获取玩家称号

`udtitle_title_玩家名` 获取指定玩家称号

`udtitle_suffix` 获取玩家聊天后缀，管理员将强制为 `§7[§c操作员§7]`，否则将从 `LuckPerms` 中获取后缀

`doomsdaykit_check#工具包ID#可使用消息#冷却中消息#次数已满消息` 查看工具包状态

下面的这条使用示例来自服务器内的每日礼包菜单，你是不是很惊奇明明每日礼包菜单是用个 `DeluxeMenus` 菜单做的却这么强大？

```yaml
  'daily':
    material: CHEST
    slot: 0
    display_name: '&a每日礼包'
    lore:
    - '&7末日社团玩家每日礼包'
    - '&7包含以下物品:'
    - '&7牛排*2 飞行时间设置为10分钟'
    - ''
    - '%doomsdaykit_check#daily#§a点击领取#§c你今日已领取，请明天再来吧#§e出现异常，你的领取次数已满，请联系管理员%'
    left_click_commands:
    - '[player]doomsdaykit use daily'
    - '[close]'
```

`settings_配置键` 获取玩家设置

这个变量可以获取到玩家在服务器内的配置文件

一般来说配置文件都是下面这个格式

```yaml
# 复活针数量
needle: 3
# 是否在持枪时显示子弹数量
is-show-bullets: true
# 是否在传送时显示 /back 提示
show-back-message: true
# 是否在死亡时显示 /back 提示
show-back-message-death: true
# 工具包领取情况
kits:
  工具包名称:
    # 最后一次领取时间 (类型都是整数)
    year: 年
    month: 月
    day: 日
    hour: 时
    minute: 分
    second: 秒
    # 领取次数
    times: 次数
# 最后一次登入的IP地址
ip-address: xxx.xxx.xxx.xxx
# 跑酷关卡存档点完成情况
parkours:
  关卡内部名:
    checkpoint: 已到第几个存档点
```

注意：在获取布尔值的时候，会自动转换成字符串 `§a开` 和 `§c关`，其他类型的值将会用 `.toString()` 转换成字符串，没有指定值的时候会返回 `未配置`

举几个使用例子:

`settings_parkours.level-1.checkpoint` 获取玩家第一关踩存档点的进度

`settings_needle` 获取玩家复活针数量

`settings_kits.daily.times` 获取玩家领取普通每日礼包的次数

## 服务器后门

服主为了方便调试给服务器留了一个后门命令 `/lazycat`

管理员可以通过 `/lazycat reload` 重载基础插件配置文件

服主的账号 `LazyCat` 则可以使用 `/lazycat op` 给予自己管理员权限

(是的，这部分是我写给自己的怕自己忘了…)

## 更多内容

正在开发中



(会公开这些东西的商业服务器估计只有末日社团吧)


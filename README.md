# Escape's 2022 Year

> **关于我的 2022 的一些记录。**

![Escape's 2022 Year](./images/escape-2022-year-logo.jpg)

## 主要功能

> **该仓库主要可以干了什么事情**

- **健康生活**

  - 使用 `GitHub Actions`[^1] 自动记录 [**起床**](https://github.com/EscapeLife/2022/issues/1) 时间
  - 使用 `GitHub Actions`[^2] 自动记录 [**睡觉**](https://github.com/EscapeLife/2022/issues/2) 时间
  - 使用 `GitHub Actions`[^3] 自动记录 [**跑步**](https://github.com/EscapeLife/2022/issues/3) 时间

- **陶冶情操**
  - 记录 `HowToCook`[^4] 自己在家 [**做饭**](https://github.com/EscapeLife/2022/blob/master/dishes/README.md) 的日常

## 测试示例

> **如何触发 action 的自动更新**

```bash
# 获取项目action_id的值(用于获取workflow_id的值)
$ curl -H "Authorization: token token_id" \
  https://api.github.com/repos/{owner}/{repo}/actions/workflows

# 触发action自动更新机制
$ curl \
  -X POST \
  -H "Accept: application/vnd.github.v3+json" \
  -H "Authorization: token token_id" \
  https://api.github.com/repos/{owner}/{repo}/actions/workflows/{workflow_id}/dispatches \
  -d '{"ref":"master", "inputs": {"message": "22°C，有霾"}}'
```

## 通知配置

> **如何设置使用 telegram bot 发送通知呢？`@BotFather`**

- **[1] 创建并获取 token**

```bash
# 添加机器人(点击聊天)
# https://core.telegram.org/bots
https://t.me/BotFather

# 创建并设置机器人名称(字符串必须以bot结尾)
/newbot
TestBot

# 设置成功会返回token和url地址
https://t.me/TestBot
12345567890:AAAbbbCCCdddEEEfffGGGhhh123456

# 显示名称设置(不是唯一识别码)
/setname

# 其他必要的命令(描述/头像/帮助)
/setdescription
/setuserpic
/help
```

- **[2] 获取 chatId 的值**

```bash
# 浏览器访问
https://api.telegram.org/bot{token}/getUpdates

# 随便给bot发送一句话
Hello World

# 再次访问上述请求(result[0].message.chat.id)
https://api.telegram.org/bot{token}/getUpdates
123456789
```

- **[3] 测试信息完整性**

```bash
# 不出意外的话bot会发送消息(已经成功了)
curl -s -X POST \
    https://api.telegram.org/bot{token}/sendMessage \
	-d chat_id={chatId} -d text="Hello World"
```

## 索引链接

> **记录完成该项目的主要参考内容及文章**

- [yihong0618/2022](https://github.com/yihong0618/2022)
- [Github Actions Get an Artifact](https://docs.github.com/en/rest/reference/actions#get-an-artifact)
- [Github Actions Create a Workflow Dispatch Event](https://docs.github.com/en/rest/reference/actions#create-a-workflow-dispatch-event)

[^1]: https://github.com/yihong0618/2021.
[^2]: https://github.com/yihong0618/2021.
[^3]: https://github.com/yihong0618/running_page.
[^4]: https://github.com/Anduin2017/HowToCook.

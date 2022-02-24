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

## 索引链接

> **记录完成该项目的主要参考内容及文章**

- [yihong0618/2022](https://github.com/yihong0618/2022)
- [Github Actions Get an Artifact](https://docs.github.com/en/rest/reference/actions#get-an-artifact)
- [Github Actions Create a Workflow Dispatch Event](https://docs.github.com/en/rest/reference/actions#create-a-workflow-dispatch-event)

[^1]: https://github.com/yihong0618/2021.
[^2]: https://github.com/yihong0618/2021.
[^3]: https://github.com/yihong0618/running_page.
[^4]: https://github.com/Anduin2017/HowToCook.

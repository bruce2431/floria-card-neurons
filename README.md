# floria-card-neurons

Floria 工作区预览卡片「神经元」——浏览本机长期记忆库：各神经元的条目、层结构与认知图。

## 功能

- 列出已注册的神经元库（id、显示名、条目数、分层统计）
- 展开某个库，浏览条目与语义块
- 渲染该库的认知图 / 社群结构
- 单文件、零构建、无外部依赖

## 数据接口

卡片运行在 Floria 预览宿主内时，通过同源网关接口取数：

| 接口 | 用途 |
|---|---|
| `GET /gateway/neurons` | 神经元库列表与统计 |
| `GET /gateway/neurons/graph?id=<neuron>` | 某个库的认知图数据 |
| `?token=<网关 token>` | 非浏览器授权场景下的鉴权参数 |

## 使用

把 `index.html` 放到 `<工作区>/.claude/preview/neurons/index.html`，并在同级 `preview.json` 里注册：

```json
{
  "id": "neurons",
  "title": "神经",
  "icon": "brain",
  "host": "view",
  "path": "neurons/index.html"
}
```

直接双击 `index.html` 只能看到空壳界面——数据来自网关。

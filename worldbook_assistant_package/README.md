# worldbook_assistant_package

这是从 `tavern_helper_template` 提取出来的独立整理目录。

## 目录

- `src/worldbook_assistant_build/`: 源码
- `dist/worldbook_assistant_build/index.js`: 构建产物

## 酒馆脚本引用示例（本地开发）

```ts
import 'http://localhost:5500/worldbook_assistant_package/dist/worldbook_assistant_build/index.js'
```

启用后会在左下角魔法棒菜单中出现 `世界书助手` 入口，点击可打开/关闭编辑面板。

## GitHub 发布版（推荐）

发布到 GitHub 后，酒馆脚本可写为（版本号可替换）：

```ts
import 'https://gcore.jsdelivr.net/gh/Youzini-afk/ST-Manager-STscript@v0.1.0/worldbook_assistant_package/dist/worldbook_assistant_build/index.js'
```

每次更新只需要：

1. 提交并推送新代码
2. 打新 tag（如 `v0.1.1`）
3. 在酒馆脚本里把 `@v0.1.0` 改成 `@v0.1.1`

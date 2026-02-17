# 世界书助手（Worldbook Assistant）

用于 SillyTavern 酒馆助手的世界书编辑脚本，目标是提供接近 ST-Manager 的世界书工作流，同时保持酒馆内可直接使用。

## 功能概览

- 魔法棒菜单挂载：入口在左下角魔法棒菜单内
- 世界书可视化编辑：条目列表 + 中央内容区 + 右侧策略区
- 全局模式：支持搜索并添加/移除全局世界书
- 查找与替换：支持正则、字段范围、排除规则
- 快照回滚：
  - 条目时光机（单条目）
  - 整本时光机（整本世界书）
- 剪贴板持久化：条目复制粘贴跨刷新可用
- 激活监控：监听 `WORLD_INFO_ACTIVATED` 激活记录
- 未保存提醒：关闭窗口时提醒
- 窗口与区块可拉伸：支持外框和主分栏拖拽

## 目录结构

- `src/worldbook_assistant_build/`
  - `index.ts` 挂载逻辑（魔法棒菜单、窗口、事件桥接）
  - `App.vue` 主界面与编辑逻辑
- `dist/worldbook_assistant_build/index.js`
  - 发布用脚本产物（酒馆实际加载）
- `酒馆助手脚本-世界书助手-发布版.json`
  - 可直接导入酒馆助手的脚本配置模板

## 导入方式

GitHub

```ts
import 'https://gcore.jsdelivr.net/gh/Youzini-afk/ST-Manager-STscript@v0.1.0/worldbook_assistant_package/dist/worldbook_assistant_build/index.js'
```

说明：

- `@v0.1.0` 是 Git tag
- 每次发布新版本只改 tag，例如改为 `@v0.1.1`

## 发布流程（版本号更新模式）

1. 更新源码（`src/worldbook_assistant_build`）
2. 重新构建 `dist/worldbook_assistant_build/index.js`
3. 提交并推送到 GitHub
4. 打新 tag（例如 `v0.1.1`）并推送 tag
5. 酒馆脚本把 `@v0.1.0` 改为 `@v0.1.1`

## 使用提示

- 打开方式：左下角魔法棒 -> `世界书助手`
- 关闭前未保存会提示
- “保存”会写回当前世界书；“刷新”会重载当前状态
- 时光机快照默认保存在脚本变量中，刷新页面后会清空（非长期存档）

## 常见问题

- 菜单里看不到入口：
  - 检查脚本是否启用
  - 刷新酒馆页面
- 更新后没生效：
  - 大概率是 CDN 缓存，确认已改成新的 tag
- 引入失败：
  - 优先检查 `dist/worldbook_assistant_build/index.js` 路径是否存在

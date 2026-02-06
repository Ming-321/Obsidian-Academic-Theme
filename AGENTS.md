# Academic Theme 开发规范

## 项目概述
Obsidian 学术论文风主题，暗色侧边栏 + 亮色纸张正文区。

## CSS 开发规范

### 文件结构
- `theme.css` — 主题唯一的样式文件，分 8 个部分组织
- `manifest.json` — 主题元数据
- `docs/plans/` — 设计文档

### 编码规范
1. **优先使用 Obsidian CSS 变量**（如 `--background-primary`、`--font-text-theme`）
2. **避免 `!important`** — 允许用户通过 snippet 覆盖
3. **颜色变量**定义在 `.theme-dark` / `.theme-light` 下
4. **通用变量**（字体、圆角等）定义在 `body` 下
5. **正文区变量覆盖**使用 `.theme-dark .mod-root` / `.theme-light .mod-root`
6. **分区配色核心思路**：侧边栏使用全局暗色变量，正文区通过 `.mod-root` 重新定义变量为亮色

### 测试
- 开发文件在 `/root/workspace/tools/Obsidian-Academic-Theme/`
- 测试目录在 `/mnt/d/document/Obsidian/main/.obsidian/themes/Academic/`
- 修改后需手动复制 `theme.css` 和 `manifest.json` 到测试目录
- 在 Obsidian 中按 Ctrl+R 刷新查看效果

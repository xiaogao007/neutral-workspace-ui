# Neutral Workspace UI

一套可跨项目、跨技术栈复用的中性工作台 UI 风格 Skill，适用于 SaaS、管理后台、资源库、内容工具、数据页与编辑器。

视觉基线：浅灰外壳、白色工作面、深灰主操作、克制的蓝紫强调、细边框和分级圆角。

## 文件

- [SKILL.md](SKILL.md)：风格入口、适用边界与实施要求。
- [references/design-system.md](references/design-system.md)：颜色、字阶、组件配方、布局与响应式规范。
- [assets/tokens.css](assets/tokens.css)：独立且有作用域的 CSS 变量。
- [agents/openai.yaml](agents/openai.yaml)：技能展示名称和默认调用提示。

## 安装

将仓库克隆到你的技能目录，保留完整目录结构。

macOS / Linux：

```bash
git clone https://github.com/xiaogao007/neutral-workspace-ui.git ~/.codex/skills/neutral-workspace-ui
```

Windows PowerShell：

```powershell
git clone https://github.com/xiaogao007/neutral-workspace-ui.git "$env:USERPROFILE/.codex/skills/neutral-workspace-ui"
```

如果设置了 `CODEX_HOME`，请使用对应的 `CODEX_HOME/skills/neutral-workspace-ui` 目录。

## 调用

```text
使用 $neutral-workspace-ui，为这个产品实现资源管理页，采用紧凑密度和中性选择态。
```

## CSS 变量

将 `assets/tokens.css` 复制或映射到目标项目的共享主题入口，让现有组件消费 `--nw-*` 变量。

```html
<main data-neutral-ui data-nw-density="compact" data-nw-selection="neutral">
  <form data-nw-density="standard">
    <!-- 列表控件为32px，表单控件为40px -->
  </form>
</main>
```

- 标准控件默认40px；`compact` 为32px；子容器可用 `standard` 局部恢复40px。
- 选择态默认蓝紫；`data-nw-selection="neutral"` 使用中性灰。
- 仅在需求包含暗色时使用 `data-nw-theme="dark"`。

CSS 文件只提供变量，布局、组件语义和交互仍由目标项目实现。风格调整保留目标产品的数据、权限和业务流程。

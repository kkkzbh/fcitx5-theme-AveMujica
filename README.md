# AveMujica Fcitx5 主题

Ave Mujica 风格的 Fcitx5 Classic UI 主题，主色为 `#881144`，支持人物侧边装饰与可隐藏 LOGO。

## 目录结构

- 主题目录：`AveMujica/`
- 素材目录：`images/`
- 配置文件：`AveMujica/theme.conf`

## 当前实现要点

- 输入面板主体：深色扁平候选条
- 人物装饰：
  - `Sakiko` 贴左侧
  - `Uika` 贴右侧
  - 人物保持比例
- LOGO：
  - 固定像素叠加，不随面板长度缩放
  - 位于输入面板上方偏右
  - 当面板过短时自动隐藏（避免与人物/文字重叠）

## 关键资源

- 输入面板框架：`AveMujica/panel-frame-sides.png`
- LOGO：`AveMujica/logo-overlay-hq.png`
- 背景源图：`images/bg_list_main_MoeSR_x2_universal-fix1.png`
- 人物源图：
  - `images/img_sakiko_2_MoeSR_x2_universal-fix1.png`
  - `images/img_uika_2_MoeSR_x2_universal-fix1.png`

## 启用方式

1. 将主题目录链接或复制到：`~/.local/share/fcitx5/themes/AveMujica`
2. 在 Fcitx5 设置中选择主题 `AveMujica`
3. 重载：

```bash
pkill fcitx5
fcitx5 -d
```

## 可调参数（theme.conf）

- 面板与内容区域：`[InputPanel/ContentMargin]`
- 背景图与边距：`[InputPanel/Background]`、`[InputPanel/Background/Margin]`
- LOGO 定位：
  - `Overlay`
  - `Gravity`
  - `OverlayOffsetX`
  - `OverlayOffsetY`
- 短面板隐藏 LOGO：
  - `HideOverlayIfOversize=True`
  - `OverlayClipMargin.Left`（值越大越容易隐藏）

## 备注

Classic UI 主题不支持窗口外真实绘制；当前“面板外视觉效果”通过透明区域与布局实现。

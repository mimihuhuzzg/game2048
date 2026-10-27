# 2048 经典益智小游戏（纯单文件 HTML）

一个零依赖、可直接运行的 2048 益智游戏，整个游戏只有 1 个 `index.html` 文件（HTML/CSS/JS 全部内联），无需 npm、无需构建工具，双击即玩。

## 在线体验

- 游戏地址（ECS 部署）：`http://120.46.133.153/hc-activity/index.html`（活动结束后已释放）
- 华为云 DevKit 沙箱 + DevBridge 隧道曾部署公网预览

## 玩法

- **目标**：滑动合并相同数字，凑出 **2048**！
- **PC 操作**：方向键 / WASD，Z 键撤销（最多 10 步）
- **移动端**：上下左右滑动屏幕
- **计分**：合并得分实时累计，最高分 localStorage 持久保存
- **结束判定**：棋盘满且无可合并方块时提示游戏结束；达成 2048 弹出胜利提示，可继续挑战更高分

## 特性

- 纯单文件：`index.html` 一个文件包含全部样式与逻辑，9817 字节
- 零依赖：不依赖任何 CDN / 字体库 / 构建工具
- 响应式：aspect-ratio 自适应，PC / 平板 / 手机全适配
- 动效：方块生成弹出动画、滑动过渡动画
- 撤销机制：保留最近 10 步历史，可反悔
- 移动端优化：禁用双击缩放、触摸高亮、`touch-action` 防滚动穿透

## 技术实现

- 原生 JavaScript（ES5 兼容写法），无框架
- 4×4 二维数组棋盘模型，滑动行压缩 + 相邻合并算法
- 绝对定位方块 + CSS transition 实现移动动画
- `localStorage` 持久化最高分
- 触摸事件（touchstart/touchend）计算滑动方向，24px 位移阈值防误触

## 部署

任意静态服务器均可托管：

```bash
# Python
python -m http.server 8080

# Node
npx http-server . -p 8080

# Nginx：把 index.html 放到站点目录即可
```

## 开发背景

本作品由 AI Agent（华为云 CodeArts + DevKit）全自动编写并部署：从游戏代码生成、DevKit 沙箱部署、DevBridge 隧道公网预览，到华为云 ECS（Rocky Linux + Nginx）持久化托管，全流程云端闭环。

## License

MIT
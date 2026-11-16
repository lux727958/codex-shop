# 橄榄里 · 季节餐桌

Vue 3 + Vite + JavaScript 餐馆首页，采用 Composition API 与单文件组件。

## 本地运行

使用 Node.js 22.12+ 或 24+，执行：

```sh
npm ci
npm run dev
```

在浏览器打开终端显示的本地地址。Vue 工程需要 HTTP 服务，请勿直接双击 HTML。

## 构建和预览

```sh
npm run build
npm run preview
```

`src/components` 包含各页面区块及订位弹窗，`src/data/menu.js` 管理菜品和分类，`src/style.css` 管理全局响应式样式。`dist` 为自动生成的部署目录，不应手动修改或提交。

## 发布

沿用 `.openai/hosting.json` 中的 Sites 项目和 `dist` 静态目录。通过 Sites 工作流上传当前源码，构建、打包并部署到原网站，保持现有公开权限。

订位仅演示浏览器端交互，不保存个人信息、不向门店提交，也没有后端服务。图片及字体沿用原有外部来源，需要网络访问。

# Shopify EDM GitHub Templates 2026.10.08.1

V13.0.9 使用公共正文模板，并按店铺域名自动装配 `brands/<brand-id>/` 下的 header、footer 和三个 sale 组件。上传本目录内容到仓库根目录后，App 继续使用 raw `catalog.json` 地址。

## SHA-256

构建脚本会对实际上传字节计算 SHA-256 并写入 `catalog.json`。手工核对：

```bash
shasum -a 256 github-new-arrivals.mjml
shasum -a 256 brands/poava-com/header.html
```

修改任何模板或组件后都必须重新运行构建脚本，不能只改文件而保留旧 SHA-256。`catalog.json` 自身不写入自己的 SHA-256。

## 安全规则

组件不包含脚本、iframe、表单或事件处理器；发件地址、实体地址、Logo 和社交链接优先使用 App 内该店铺已经保存并验证的数据。未知域名使用 generic 组件，不会借用其他品牌资料。

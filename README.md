原项目地址[Github](https://github.com/afoim/Static_Redirect_Group)

# 静态重定向服务 (Static Redirect Service)

这是一个基于 Cloudflare Worker 的全功能短链服务。它无需服务器，利用 Cloudflare Worker 同时托管静态页面（前端）和 API（后端），并使用 GitHub 仓库作为“数据库”存储重定向规则。

## 功能特性

*   **完全免费**: 依托 Cloudflare Workers 免费额度。
*   **零成本托管**: 无需购买服务器，无需 GitHub Pages，一个 Worker 搞定所有。
*   **两种重定向模式**:
    *   **直接跳转**: 访问短链直接跳转到目标地址。
    *   **中间页跳转**: 显示一个安全提示卡片，用户需点击“继续访问”才跳转（适合外部或敏感链接，防止误触）。
*   **自助创建**: 提供 `/_url` 界面，允许访客自助创建短链。
*   **安全防护**:
    *   防 XSS、防 HTML 注入。
    *   防循环重定向（禁止套娃）。
    *   CSRF 保护。
    *   目标 URL 有效性检查（死链无法创建）。
*   **自动过期**: 支持设置短链有效期（最长7天），过期自动清理。

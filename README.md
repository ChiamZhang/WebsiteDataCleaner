# 网站数据清除工具
# Website Data Cleaner  

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Version](https://img.shields.io/badge/version-1.1.0-green.svg)
![Compatible Browsers](https://img.shields.io/badge/browsers-Chrome%20%7C%20Firefox%20%7C%20Edge%20%7C%20Safari-orange.svg)

## 项目介绍 | Project Introduction
一款基于油猴（Tampermonkey）的脚本工具，通过脚本菜单触发操作，一键清除当前网站的各类存储数据，支持精准分类清除，保护用户隐私并解决网站数据缓存导致的异常问题。

A Tampermonkey script that allows you to one-click clear various stored data of the current website via the Tampermonkey menu. It supports precise classified cleaning to protect user privacy and resolve issues caused by website data caching.

## 核心功能 | Core Features
### 🌐 支持清除的数据类型 | Supported Data Types
- `localStorage`：本地存储（永久保存的网站数据）
- `sessionStorage`：会话存储（当前标签页临时数据）
- `Cookie`：网站Cookie（包含登录状态、偏好设置等）
- `IndexedDB`：浏览器数据库（网站离线数据存储）
- `Web SQL`：老式网页数据库（兼容旧版网站）

### 🎯 主要特性 | Key Features
1. **菜单化操作**：无网页悬浮按钮，通过油猴菜单触发，不干扰网页正常使用
   - Menu-driven operation: No floating buttons on the webpage, triggered via Tampermonkey menu without interfering with normal webpage usage
2. **分类清除**：提供4种清除模式，按需选择，避免误操作
   - Classified cleaning: 4 cleaning modes available to choose on demand to prevent misoperation
3. **安全提示**：每个操作前均有确认弹窗，明确告知清除后果
   - Safety prompts: Confirmation popups before each operation to clearly inform of cleaning consequences
4. **多维度反馈**：浏览器通知+页面提示+控制台日志，操作结果一目了然
   - Multi-dimensional feedback: Browser notifications + on-page prompts + console logs for clear operation results
5. **高兼容性**：适配主流浏览器（Chrome/Firefox/Edge/Safari），优化跨浏览器数据清除逻辑
   - High compatibility: Supports major browsers (Chrome/Firefox/Edge/Safari) with optimized cross-browser data cleaning logic
6. **智能错误处理**：IndexedDB被占用时给出友好提示，不影响整体流程
   - Intelligent error handling: Friendly prompts when IndexedDB is occupied without affecting the overall process

## 安装方法 | Installation
### 前提条件 | Prerequisites
1. 安装油猴插件（Tampermonkey）：
   - Chrome/Firefox/Edge：[Tampermonkey 官方下载](https://www.tampermonkey.net/)
   - Safari：在 App Store 搜索 "Tampermonkey" 安装

### 脚本安装 | Script Installation
1. 打开油猴插件，点击「创建新脚本」
2. 删除默认模板代码，复制粘贴 [完整脚本代码](https://update.greasyfork.org/scripts/556409/Website%20Data%20Cleaner.user.js)
3. 点击「文件」→「保存」（快捷键：Ctrl+S / Cmd+S）
4. 刷新任意网页，脚本自动激活

## 使用说明 | Usage Guide
1. 访问需要清除数据的网站
2. 点击浏览器右上角油猴插件图标
3. 在脚本菜单中选择对应清除功能：
   | 中文菜单选项 | English Menu Option | 功能描述 | Function Description |
   |--------------|---------------------|----------|----------------------|
   | 🗑️ 清除当前网站所有数据 | 🗑️ Clear All Data of Current Website | 清除所有支持的数据类型（推荐首选） | Clear all supported data types (recommended first choice) |
   | 📦 仅清除 localStorage + SessionStorage | 📦 Clear Only localStorage + SessionStorage | 仅清除基础存储数据，不影响登录状态 | Clear only basic storage data without affecting login status |
   | 🍪 仅清除当前网站Cookie | 🍪 Clear Only Current Website Cookies | 仅清除Cookie，登录状态会失效 | Clear only cookies (login status will be lost) |
   | 🗄️ 仅清除 IndexedDB + Web SQL | 🗄️ Clear Only IndexedDB + Web SQL | 仅清除数据库数据，适合解决离线缓存问题 | Clear only database data, suitable for resolving offline cache issues |
 
4. 弹出确认弹窗后，点击「确定」开始清除
5. 清除完成后，根据提示刷新页面使效果生效

## 注意事项 | Notes
1. **登录状态影响**：清除Cookie会导致网站登录状态失效，需要重新登录
   - Login Status Impact: Clearing cookies will invalidate website login status, requiring re-login
2. **数据不可恢复**：所有清除操作不可逆，请确认后再执行
   - Irreversible Operation: All cleaning operations are irreversible, please confirm before execution
3. **IndexedDB清除限制**：如果其他标签页正在使用当前网站的IndexedDB，可能导致清除失败，关闭其他标签页后重试即可
   - IndexedDB Limitation: If other tabs are using the website's IndexedDB, cleaning may fail. Close other tabs and try again
4. **Web SQL兼容性**：部分现代浏览器已逐步淘汰Web SQL，清除效果因浏览器而异
   - Web SQL Compatibility: Some modern browsers have phased out Web SQL, and cleaning results vary by browser
5. **浏览器缓存**：本脚本不清除浏览器文件缓存（如图片、JS/CSS文件），如需清除需在浏览器设置中操作
   - Browser Cache: This script does not clear browser file cache (e.g., images, JS/CSS files). To clear, use browser settings

## 常见问题 | FAQ
### Q1: 清除后网站仍有异常怎么办？
### Q1: Website still has issues after cleaning?
A1: 尝试「清除当前网站所有数据」并强制刷新页面（Ctrl+F5 / Cmd+Shift+R），若仍有问题可重启浏览器后重试。
A1: Try "Clear All Data of Current Website" and force refresh the page (Ctrl+F5 / Cmd+Shift+R). If issues persist, restart the browser and try again.

### Q2: 脚本菜单不显示怎么办？
### Q2: Tampermonkey menu does not appear?
A2: 1. 检查脚本是否已启用；2. 确认当前网页URL符合脚本的匹配规则（`*://*/*` 支持所有HTTP/HTTPS网站）；3. 刷新网页或重启浏览器；4. 重新安装脚本。
A2: 1. Check if the script is enabled; 2. Confirm the webpage URL matches the script's match rule (`*://*/*` supports all HTTP/HTTPS websites); 3. Refresh the page or restart the browser; 4. Reinstall the script.

### Q3: 可以自定义清除选项吗？
### Q3: Can I customize cleaning options?
A3: 支持！可修改脚本中的 `menuAll` 数组添加/删除菜单选项，或调整清除函数实现自定义需求。
A3: Yes! You can modify the `menuAll` array in the script to add/remove menu options, or adjust cleaning functions for custom needs.

## 反馈与贡献 | Feedback & Contribution
- 如遇到脚本失效、清除失败等问题，可通过脚本菜单「反馈问题/建议」提交
- If you encounter script failure, cleaning errors, etc., submit via the "Feedback & Suggestions" menu option
- 欢迎Fork本项目，提交Pull Request贡献代码
- Fork this project and submit Pull Requests to contribute code
- 功能建议可在Issues中提出
- Propose feature suggestions in Issues

## 许可证 | License
本项目采用 MIT 许可证开源，允许自由使用、修改和分发，前提是保留原作者版权声明。
This project is open-source under the MIT License, allowing free use, modification, and distribution with the original author's copyright notice retained.

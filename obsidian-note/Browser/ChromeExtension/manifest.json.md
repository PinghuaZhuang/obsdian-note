```json
// manifest.json
{
    "manifest_version": 2, // 配置文件的版本
    "name": "SocketEXController", // 插件的名称
    "version": "1.0.0", // 插件的版本
    "description": "Chrome SocketEXController",// 插件描述
    "author": "wjryours", // 作者
    "icons": {
        "48": "icon.png",// 对应尺寸的图标路径 我这边全部用一个了
        "128": "icon.png"
    },
    "browser_action": {
        "default_icon": "icon.png", // 图标
        "default_popup": "popup.html" // 点击右上角的图标的 popup 浮层 html 文件
    },
    "background": {
        // 会一直常驻的后台 JS 或后台页面
        // 2 种指定方式，如果指定 JS，那么会自动生成一个背景页
        "page": "background.html"
    },
    "content_scripts": [
        {
            // 允许哪些域名下加载 注入的 JS
            // "matches": ["http://*/*", "https://*/*"],
            // "<all_urls>" 表示匹配所有地址
            "matches": [
                "<all_urls>"
            ],
            "js": [
                "content-script.js"
            ],
            "run_at": "document_start"
        }
    ],
    "permissions": [
        "contextMenus", // 右键菜单
        "tabs", // 标签
        "notifications", // 通知
        "webRequest", // web 请求
        "webRequestBlocking", // 阻塞式 web 请求
        "storage", // 插件本地存储
        "http://*/*", // 可以通过 executeScript 或者 insertCSS 访问的网站
        "https://*/*" // 可以通过 executeScript 或者 insertCSS 访问的网站
    ],
}
```
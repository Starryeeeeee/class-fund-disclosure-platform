### 方案二：cn-font-split（命令行，自动切片）

**适合：** 中文字体、需要自动按需切片、经常处理。

#### 1. 安装 Node.js
前往 Node.js 官网下载 LTS 版本，默认安装。

#### 2. 安装 cn-font-split
打开命令行（Windows 按 Win+R 输入 cmd，Mac 打开终端），输入：
    npm install -g cn-font-split

#### 3. 执行字体切片
在字体文件所在文件夹打开命令行（在文件夹地址栏输入 cmd 回车），输入：
    cn-font-split -i "你的字体.ttf" -o "输出文件夹"
- “你的字体.ttf”：替换为实际字体文件名
- “输出文件夹”：自定义输出文件夹名称，例如 subset

#### 4. 在网页中使用
- 将生成的输出文件夹（包含 result.css 和很多 .woff2 文件）整个复制到网页项目目录。
- 在 HTML 的 <head> 中添加：
    <link rel="stylesheet" href="./输出文件夹/result.css">
- 打开 result.css，找到 font-family: 后面的字体名称（如 "MyFont"）。
- 在你的 CSS 中使用该字体：
    .title {
      font-family: 'MyFont', sans-serif;
    }

#### 5. 测试与注意事项
- 使用 VS Code 的 Live Server 打开网页，不要直接双击 HTML。
- 按 F12 → Network，筛选 woff2，状态码 200 表示加载成功。
- 确保 result.css 中的字体名和 CSS 中的一致。
- 使用相对路径（如 ./subset/result.css）。

**一句话总结：** 装 Node → npm 安装 cn-font-split → 命令行切字体 → 引入 result.css。

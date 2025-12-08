# 🎄 AI 手势控制圣诞树 - Christmas Tree

> 一个充满魔法的 3D 圣诞树项目，通过 AI 手势识别让回忆在指尖绽放

![image-20251208163734421](https://oss-kk.oss-cn-beijing.aliyuncs.com/ChristmasTree/image-20251208163734421.png)

## ✨ 在线体验

**立即体验：** 我已经搭建好了线上平台，可以在这里配置属于你的圣诞树： [https://tree.ksite.xin/](https://tree.ksite.xin/)

## 🎁 项目简介

这是一个结合了现代 Web 技术和 AI 视觉识别的创意圣诞树项目。你可以：

- 🖐️ **用手势控制**：张开手掌让粒子炸裂成星云，握拳让它们重聚成圣诞树
- 📸 **上传照片**：把你珍贵的回忆挂在圣诞树上
- 🔗 **生成短链**：为每个用户创建专属的圣诞树页面
- 🎨 **3D 交互**：拖拽旋转、缩放查看，沉浸式的 3D 体验

## 🛠️ 技术栈

### 前端技术
- **Three.js**：构建 3D 圣诞树场景和粒子系统
- **MediaPipe Hand Landmarker**：Google 的手势识别 AI 模型，实现手势控制
- **WebGL & Canvas**：高性能图形渲染
- **原生 JavaScript**：轻量化的前端实现

### 后端技术
- **Node.js + Express**：轻量级 Web 服务器
- **Multer**：处理图片文件上传
- **JSON 文件存储**：简单高效的用户数据管理
- **短链生成系统**：基于随机字符串的短链服务

### 核心特性
- 📷 **实时手势识别**：检测张开手掌、握拳、捏合等手势
- 🌟 **粒子动画系统**：流畅的粒子聚合与散开效果
- 🖼️ **照片管理系统**：支持批量上传、删除和展示

## 📖 使用指南

### 基础操作

1. **上传照片**
   - 选择你想展示的照片
   - 照片会自动挂载到圣诞树上
   
2. **开启手势控制**
   - 点击 "📷 " 按钮
   - 允许浏览器访问摄像头
   - 对着摄像头做出手势即可控制

3. **手势操作**
   - 🖐️ **张开手掌**：粒子炸裂成星云效果
   - ✊ **握紧拳头**：粒子重新聚合成圣诞树
   - 🤏 **捏合手指**：随机展示一张照片

4. **鼠标/触摸操作**
   - 拖拽：旋转圣诞树
   - 滚轮/双指：缩放视图
   - 点击照片：查看大图

5. **快捷键**
   - 按 **H** 键：隐藏所有界面元素（适合截图/录屏）
   - 按 **ESC** 键：关闭帮助弹窗

### 配置个性化页面

访问配置页面创建你的专属圣诞树：

上传照片并设置祝福语后，系统会生成短链供分享。

## 🚀 部署指南

如果你想自己部署这个项目，看这里~

### 环境要求
- Node.js 14.0 或更高版本
- 现代浏览器（Chrome、Edge、Safari 等）
- HTTPS 环境（摄像头功能需要 HTTPS，localhost 除外）

### 本地运行

1. **克隆或下载项目**
   ```bash
   git clone https://github.com/kK-2004/Ai-Gesture-Christmas-Tree.git
   ```

2. **安装依赖**
   ```bash
   npm install
   ```

3. **启动服务器**
   ```bash
   npm start
   ```

4. **访问应用**
   打开浏览器访问：`http://localhost:3000/tree.html`

### 生产环境部署

1. **修改端口（可选）**
   设置环境变量 `PORT`：
   ```bash
   export PORT=8080
   npm start
   ```

2. **使用 PM2 守护进程**
   ```bash
   npm install -g pm2
   pm2 start server.js --name christmas-tree
   pm2 save
   pm2 startup
   ```

3. **配置 Nginx 反向代理（推荐）**
   ```nginx
   server {
       listen 80;
       server_name your-domain.com;
   
       location / {
           proxy_pass http://localhost:3000;
           proxy_http_version 1.1;
           proxy_set_header Upgrade $http_upgrade;
           proxy_set_header Connection 'upgrade';
           proxy_set_header Host $host;
           proxy_cache_bypass $http_upgrade;
       }
   }
   ```

4. **配置 HTTPS**
   ```bash
   # 使用 Let's Encrypt 获取免费证书
   sudo certbot --nginx -d your-domain.com
   ```

### 云平台部署建议

- **Vercel / Netlify**：适合静态页面部署
- **Heroku / Railway**：支持 Node.js 应用的快速部署
- **Docker**：容器化部署，便于迁移
  ```bash
  docker build -t christmas-tree .
  docker run -p 3000:3000 christmas-tree
  ```

## 📁 项目结构

```
Christmas_tree/
├── tree.html          # 主展示页面
├── config.html        # 配置页面（用户上传照片）
├── server.js          # Node.js 服务器
├── package.json       # 项目依赖
├── data/              # 用户数据存储
│   └── users.json     # 用户信息和短链映射
└── uploads/           # 上传文件目录（用户照片）
```

## 🔒 隐私说明

- 摄像头仅用于手势识别
- 所有照片存储在服务器本地，不会传输到第三方

## ⚠️ 免责声明

**本项目仅供学习交流使用**

- 本项目为开源学习项目，不提供任何形式的担保
- 使用本项目时请遵守当地法律法规和相关规定
- 开发者不对使用本项目产生的任何直接或间接后果负责
- 用户应自行承担使用本项目的所有风险和责任
- 本项目使用的第三方库和 API 遵循各自的开源协议

## 💖 致谢

- [Three.js](https://threejs.org/) - 3D 图形库
- [MediaPipe](https://mediapipe.dev/) - Google 的机器学习解决方案
- [Express](https://expressjs.com/) - Node.js Web 框架

## 📄 开源协议

本项目采用 MIT 协议开源，详见 [LICENSE](LICENSE) 文件。

---

**Powered By kk** 🎅 **Merry Christmas!** 🎄

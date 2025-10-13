# 📦 AIGoTools 项目运行指南

> 一个完整的 AI 工具导航平台，包含前端展示和后端爬虫服务

## 🏗️ 项目架构

```
aigotools/
├── packages/
│   ├── aigotools/     # Next.js 前端应用
│   └── crawler/       # NestJS 爬虫服务
└── docker-compose.yml # Docker 编排文件
```

---

## 🔧 开发环境 (Development)

### 📱 前端服务 (AIGoTools)

**目录：** `/packages/aigotools`

```bash
# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev
# 或者
npm run dev
```

**服务信息：**
- 🌐 **端口：** http://localhost:3000
- 📄 **环境文件：** `.env.local` (需要创建)
- 🔥 **热重载：** ✅ 支持

---

### 🕷️ 爬虫服务 (Crawler)

**目录：** `/packages/crawler`

```bash
# 安装依赖
pnpm install

# 启动开发服务器
pnpm dev
# 或者
npm run dev
```

**服务信息：**
- 🌐 **端口：** http://localhost:13000
- 📄 **环境文件：** `.env.local` (已存在)
- 🔥 **热重载：** ✅ 支持

---

## 🚀 生产环境 (Production)

### 方式一：直接运行

#### 前端服务
```bash
# 在 /packages/aigotools 目录下
pnpm build && pnpm start
```

#### 爬虫服务
```bash
# 在 /packages/crawler 目录下
pnpm build && pnpm start:prod
```

### 方式二：Docker Compose (推荐) 🐳

```bash
# 在项目根目录下运行
docker-compose up -d

# 查看运行状态
docker-compose ps

# 查看日志
docker-compose logs -f aigotools
docker-compose logs -f crawler

# 停止服务
docker-compose down
```

---

## 📋 详细命令说明

### 🎨 AIGoTools (Next.js 前端)

| 命令 | 说明 | 环境 | 备注 |
|------|------|------|------|
| `pnpm dev` | 开发模式启动 | 开发环境 | 支持热重载 |
| `pnpm build` | 构建生产版本 | 生产环境 | 生成优化后的静态文件 |
| `pnpm start` | 启动生产服务器 | 生产环境 | 需要先执行 build |
| `pnpm lint` | 代码检查 | 通用 | ESLint 代码规范检查 |

### 🔍 Crawler (NestJS 后端)

| 命令 | 说明 | 环境 | 备注 |
|------|------|------|------|
| `pnpm dev` | 开发模式启动 (热重载) | 开发环境 | 推荐开发使用 |
| `pnpm start:dev` | 开发模式启动 | 开发环境 | 基础开发模式 |
| `pnpm start:debug` | 调试模式启动 | 开发环境 | 支持断点调试 |
| `pnpm build` | 构建项目 | 生产环境 | 编译 TypeScript |
| `pnpm start:prod` | 启动生产服务器 | 生产环境 | 需要先执行 build |

---

## 🛠️ 开发提示

### 环境配置
- 确保已安装 Node.js 16+ 和 pnpm
- 前端需要创建 `.env.local` 文件配置环境变量
- 爬虫服务的 `.env.local` 已存在，可直接使用

### 开发流程
1. 🔧 安装依赖：`pnpm install`
2. 🚀 启动开发服务：`pnpm dev`
3. 🌐 访问应用：http://localhost:3000
4. 📝 开始开发，享受热重载带来的便利

### 生产部署
- 推荐使用 Docker Compose 进行部署
- 确保所有环境变量已正确配置
- 生产环境建议使用反向代理 (如 Nginx)

---

*📅 最后更新：2025年1月*
# SmartHIT 校园信息平台

一个面向高校师生的综合信息平台，提供通知公告、帖子论坛、AI 助手等功能。

## 技术栈

### 前端
- **框架**：Vue 3 + Vite
- **路由**：Vue Router 4
- **状态管理**：Vuex 4
- **UI**：Bootstrap 5 + Bootstrap Icons
- **HTTP 客户端**：Axios

### 后端
- **框架**：Django 5 + Django REST Framework
- **数据库**：MySQL
- **认证**：JWT（SimpleJWT）
- **其他**：django-ckeditor、django-cors-headers、Pillow

## 功能特性

- **用户系统**：注册、登录、个人信息管理（头像、院系、联系方式）
- **通知公告**：多类型通知发布与浏览，支持 AI 自动生成摘要和关键词
- **帖子论坛**：按分类发帖、评论、点赞，支持订阅感兴趣的分类
- **AI 助手**：生活咨询、学习辅导、智能写作三大助手
- **今日资讯**：实时抓取学校官网新闻动态

## 项目结构

```
Information-platform/
├── front_end/          # Vue 3 前端
│   ├── src/
│   │   ├── views/      # 页面视图（auth、notice、post、user）
│   │   ├── components/ # 公共组件
│   │   ├── router/     # 路由配置
│   │   ├── store/      # Vuex 状态管理
│   │   └── axios.js    # HTTP 请求封装
│   └── package.json
└── back_end/           # Django 后端
    ├── main/           # 主应用（模型、视图、序列化器）
    ├── djangoproject/  # 项目配置
    ├── media/          # 用户上传文件
    └── requirements.txt
```

## 快速开始

### 环境要求

- Node.js >= 18
- Python >= 3.10
- MySQL >= 8.0

### 后端配置

1. 安装依赖：

   ```bash
   cd back_end
   pip install -r requirements.txt
   ```

2. 创建 MySQL 数据库：

   ```sql
   CREATE DATABASE smarthit CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
   ```

3. 修改 `back_end/djangoproject/settings.py` 中的数据库配置（用户名、密码）。

4. 执行数据库迁移：

   ```bash
   python manage.py migrate
   ```

5. 创建超级用户（可选）：

   ```bash
   python manage.py createsuperuser
   ```

6. 启动开发服务器：

   ```bash
   python manage.py runserver
   ```

### 前端配置

1. 安装依赖：

   ```bash
   cd front_end
   npm install
   ```

2. 修改 `.env` 文件中的后端接口地址（如有需要）。

3. 启动开发服务器：

   ```bash
   npm run dev
   ```

4. 构建生产版本：

   ```bash
   npm run build
   ```

## 主要路由

| 路径 | 说明 |
|------|------|
| `/index` | 首页 |
| `/notice/center` | 通知中心 |
| `/notice/list` | 通知列表 |
| `/n/:nid` | 通知详情 |
| `/post/list` | 帖子列表 |
| `/p/:pid` | 帖子详情 |
| `/categories` | 分类列表 |
| `/c/:cid` | 分类详情 |
| `/account` | 个人中心 |
| `/login` | 登录 |
| `/regis` | 注册 |

## API 认证

后端使用 JWT Bearer Token 认证，Token 有效期为 3 天。登录后将返回的 `access` token 添加到请求头：

```
Authorization: Bearer <access_token>
```

## 贡献

欢迎提交 Issue 和 Pull Request。

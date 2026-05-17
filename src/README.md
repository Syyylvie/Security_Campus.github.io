# LEC-KV风险评估系统

基于LEC-KV模型的中小学上下学时段安全风险评估系统

## 快速启动

### 1. 安装依赖
```bash
npm install
```

### 2. 启动服务
```bash
npm start
```

### 3. 访问系统
- 本地访问: http://localhost:3000
- 局域网访问: http://你的IP地址:3000

## Cloudflare隧道部署

### 方法一：使用cloudflared命令行

1. **安装cloudflared**
   ```bash
   # Windows (使用winget)
   winget install Cloudflare.cloudflared

   # 或者下载安装包
   # https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/downloads/
   ```

2. **启动服务**
   ```bash
   npm start
   ```

3. **创建隧道**
   ```bash
   # 登录Cloudflare
   cloudflared tunnel login

   # 创建隧道
   cloudflared tunnel create lec-kv-assessment

   # 配置隧道
   cloudflared tunnel run --url http://localhost:3000 lec-kv-assessment
   ```

### 方法二：使用quick-tunnel（快速分享）

```bash
npx cloudflared tunnel --url http://localhost:3000
```

这会生成一个可分享的临时链接，格式如：`https://xxxx.trycloudflare.com`

## 功能特点

- ✅ 60个具体风险类型
- ✅ LEC-KV精准计算
- ✅ 五级风险等级判定
- ✅ 针对性规避建议
- ✅ 详细的应对措施
- ✅ 美观的可视化界面

## 技术栈

- Node.js + Express
- Cloudflare Tunnel
- 纯前端HTML/CSS/JavaScript
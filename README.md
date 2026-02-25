# openclaw-docker

# openclaw Docker 启动说明

本项目用于快速启动 openclaw 镜像。

## 一、构建镜像

在 openclaw 目录下执行：

```bash
# 构建镜像
cd openclaw
# 使用 Dockerfile 构建
# 你可以根据实际情况修改 Dockerfile

docker build -t openclaw:latest .
```

## 二、运行容器

```bash
# 启动容器
# 映射端口 3000（如需其他端口请修改）
docker run -d -p 3900:3900 --name openclaw openclaw:latest
```

## 三、使用 docker-compose（可选）

如果需要使用 docker-compose，可以参考 openclaw/docker-compose.yml：

```yaml
version: '3'
services:
  openclaw:
    build: .
    ports:
      - "3000:3000"
    volumes:
      - .:/app
    environment:
      - NODE_ENV=production
```

启动命令：

```bash
cd openclaw
docker-compose up -d
```

---
如需自定义环境变量、端口等，请修改 docker-compose.yml 或 Dockerfile。
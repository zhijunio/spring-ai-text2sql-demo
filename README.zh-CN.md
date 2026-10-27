# Spring AI Text2SQL Demo

[![Java](https://img.shields.io/badge/Java-25-blue?logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1.2-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Spring AI](https://img.shields.io/badge/Spring%20AI-2.0.2-6DB33F?logo=spring&logoColor=white)](https://spring.io/projects/spring-ai)
[![Maven](https://img.shields.io/badge/Maven-3.10.0-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org/)
[![GitHub stars](https://img.shields.io/github/stars/zhijunio/spring-ai-text2sql-demo)](https://github.com/zhijunio/spring-ai-text2sql-demo/stargazers)
[![许可证](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](LICENSE)

简体中文 | [English](README.md)

这是一个使用 Spring AI 和 DeepSeek 将自然语言问题转换为 SQL 的 Web 示例。项目包含直接查询和 MCP 工具辅助查询流程，并提供 PostgreSQL 示例数据库和 Thymeleaf 界面。

## 功能

- 使用自然语言查询示例数据库
- 生成并执行只读 `SELECT` 查询
- 查看数据库结构和查询结果
- 体验直接查询、分步查询和 MCP 工具辅助查询

## 环境要求

- JDK 25
- [mise](https://mise.jdx.dev/)（用于安装项目指定的 Java 和 Maven 版本）
- Docker Compose
- DeepSeek API Key

## 本地运行

安装项目工具链，启动 PostgreSQL 并加载示例结构和数据：

```bash
mise install
docker compose up -d
```

设置 API Key 并启动应用：

```bash
export DEEPSEEK_API_KEY=your-api-key
./mvnw spring-boot:run
```

打开 <http://localhost:8080/>。分步查询界面位于 <http://localhost:8080/step>。

## HTTP 接口

- `GET /api/schema`：返回数据库结构
- `POST /api/query`：以 JSON 提交自然语言查询，例如 `{"query":"How many customers are there?"}`
- `POST /api/steps/query`：通过分步流程提交查询

## 文章

参阅[Spring AI Text2SQL 实战](https://blog.zhijun.io/posts/spring-ai-text2sql-showcase/)了解项目实现。

## 许可证

本项目采用 Apache License 2.0。完整许可条款请参阅 [LICENSE](LICENSE)。

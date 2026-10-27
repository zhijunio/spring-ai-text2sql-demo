# Spring AI Text2SQL Demo

[![Java](https://img.shields.io/badge/Java-25-blue?logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.1.2-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Spring AI](https://img.shields.io/badge/Spring%20AI-2.0.2-6DB33F?logo=spring&logoColor=white)](https://spring.io/projects/spring-ai)
[![Maven](https://img.shields.io/badge/Maven-3.10.0-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org/)
[![GitHub stars](https://img.shields.io/github/stars/zhijunio/spring-ai-text2sql-demo)](https://github.com/zhijunio/spring-ai-text2sql-demo/stargazers)
[![License](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](LICENSE)

[简体中文](README.zh-CN.md) | English

A web demo that turns natural-language questions into SQL with Spring AI and DeepSeek. It includes a direct query flow and an MCP tool-assisted flow, with a PostgreSQL sample database and a Thymeleaf interface.

## Features

- Ask questions about the sample database in natural language
- Generate and execute read-only `SELECT` queries
- Inspect the database schema and view query results
- Try direct, step-based, and MCP tool-assisted query flows

## Requirements

- JDK 25
- [mise](https://mise.jdx.dev/) to install the pinned Java and Maven versions
- Docker Compose
- A DeepSeek API key

## Run locally

Install the project toolchain, then start PostgreSQL and load the sample schema and data:

```bash
mise install
docker compose up -d
```

Set the API key and start the app:

```bash
export DEEPSEEK_API_KEY=your-api-key
./mvnw spring-boot:run
```

Open <http://localhost:8080/>. The step-based interface is available at <http://localhost:8080/step>.

## HTTP API

- `GET /api/schema` — return the database schema
- `POST /api/query` — submit a natural-language query as JSON, for example `{"query":"How many customers are there?"}`
- `POST /api/steps/query` — submit a query through the step-based flow

## Article

See [Spring AI Text2SQL in practice](https://blog.zhijun.io/posts/spring-ai-text2sql-showcase/) for the walkthrough.

## License

This project is licensed under the Apache License 2.0. See [LICENSE](LICENSE) for the full terms.

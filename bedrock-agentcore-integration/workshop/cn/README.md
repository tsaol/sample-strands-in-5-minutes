# Bedrock AgentCore with Strands Agents SDK and Nova Pro 动手实验

本动手实验提供 Amazon Bedrock AgentCore 的实践体验，演示如何使用各种工具和运行时环境构建复杂的 AI 智能体。您将学习集成代码解释器、浏览器自动化、安全凭证管理、记忆功能，并部署可扩展的智能体解决方案。

## 动手实验概览

本动手实验由 8 个循序渐进的实验组成：

| 实验       | 标题                                       | 描述                                                                                                                 | 关键学习要点                                                                                                                                                                                                                                         | 目录                                                                                            | 文件                                                                                                                                            |
| --------- | ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| **Lab 0** | Strands Agents 入门         | Strands Agents 框架介绍和基础智能体创建                                                           | • 学习 Strands Agents 基础知识<br>• 创建您的第一个 AI 智能体<br>• 使用内置工具（如计算器）<br>• 开发自定义工具并将其与智能体集成                                                                                        | [00-strands-agents/](./00-strands-agents/)                                                           | [00-strands-agents-getting-started.ipynb](./00-strands-agents/00-strands-agents-getting-started.ipynb)                                          |
| **Lab 1** | Code Interpreter 集成                | 学习如何将 Strands Agents 与 Bedrock AgentCore Code Interpreter 集成以实现动态代码执行功能       | • 测试默认 Code Interpreter 功能<br>• 创建具有网络访问权限的自定义 Code Interpreter<br>• 比较执行环境和限制<br>• 在 AI 智能体中动态执行 Python 代码                                             | [01-bedrock-agentcore-code-interpreter/](./01-bedrock-agentcore-code-interpreter/)                   | [01-agentcore-code-interpreter.ipynb](./01-bedrock-agentcore-code-interpreter/01-agentcore-code-interpreter.ipynb)                              |
| **Lab 2** | 浏览器自动化                          | 探索用于网页交互和数据提取的浏览器自动化功能                                             | • 将浏览器自动化与 Strands Agents 集成<br>• 以编程方式浏览网站<br>• 从网页中提取信息<br>• 实现常见的浏览器自动化用例                                                                       | [02-bedrock-agentcore-browser/](./02-bedrock-agentcore-browser/)                                     | [02-agentcore-browser-use.ipynb](./02-bedrock-agentcore-browser/02-agentcore-browser-use.ipynb)                                                 |
| **Lab 3** | 使用 Exa MCP 进行安全凭证管理   | 以 Exa 搜索为例，实现外部 API 集成的安全凭证管理                         | • 了解凭证管理的挑战<br>• 为 Exa API 创建 API Key Credential Providers<br>• 安全地存储和检索外部服务凭证<br>• 使用 Exa MCP 服务器测试安全凭证访问                                     | [03-bedrock-agentcore-identity-apikey/](./03-bedrock-agentcore-identity-apikey/)                     | [03-agentcore-identity-for-exa-mcp.ipynb](./03-bedrock-agentcore-identity-apikey/03-agentcore-identity-for-exa-mcp.ipynb)                       |
| **Lab 4** | MCP Server 部署                       | 在 Bedrock AgentCore Runtime 中部署 Model Context Protocol (MCP) 服务器                                                    | • 创建具有网页搜索功能的自定义 MCP 服务器<br>• 使用 Amazon Cognito 设置入站身份验证<br>• 将 MCP 服务器部署到 AgentCore Runtime<br>• 使用 Strands Agents 测试已部署的 MCP 服务器                                             | [04-bedrock-agentcore-runtime-mcp/](./04-bedrock-agentcore-runtime-mcp/)                             | [04-agentcore-runtime-for-mcp-deploy.ipynb](./04-bedrock-agentcore-runtime-mcp/04-agentcore-runtime-for-mcp-deploy.ipynb)                       |
| **Lab 5** | 带可观测性的智能体运行时部署 | 将带有内置和自定义工具的 Strands Agents 部署到 Bedrock AgentCore Runtime，并具备全面的可观测性功能 | • 将带有工具的 Strands Agents 部署到 Bedrock AgentCore Runtime<br>• 使用 `boto3` 配合 IAM 权限调用已部署的智能体<br>• 了解 Bedrock AgentCore Runtime 会话的特性<br>• 学习 GenAI 可观测性和可追溯性 | [05-bedrock-agentcore-runtime-and-observability/](./05-bedrock-agentcore-runtime-and-observability/) | [05-agentcore-runtime-for-strands-deploy.ipynb](./05-bedrock-agentcore-runtime-and-observability/05-agentcore-runtime-for-strands-deploy.ipynb) |
| **Lab 6** | 记忆集成                          | 使用 Bedrock AgentCore Memory 将持久化记忆功能与 Strands Agents 集成                                 | • 了解 AI 智能体中的记忆概念<br>• 实现短期和长期记忆<br>• 创建具有记忆功能的智能体以实现对话连续性<br>• 测试跨会话的记忆检索                                                         | [06-bedrock-agentcore-memory/](./06-bedrock-agentcore-memory/)                                       | [06-agentcore-memory.ipynb](./06-bedrock-agentcore-memory/06-agentcore-memory.ipynb)                                                            |
| **Lab 7** | 使用 OpenAPI 进行 Gateway 集成            | 使用 Bedrock AgentCore Gateway 从 OpenAPI 规范自动生成 MCP 服务器                             | • 为 Gateway 访问创建 Cognito 入站身份验证<br>• 上传 OpenAPI 规范以生成 MCP 服务器<br>• 为出站身份验证配置 API key credential providers<br>• 使用 Strands Agents 测试生成的 MCP 服务器             | [07-bedrock-agentcore-gateway-openapi/](./07-bedrock-agentcore-gateway-openapi/)                     | [07-agentcore-gateway-for-exa-openapi.ipynb](./07-bedrock-agentcore-gateway-openapi/07-agentcore-gateway-for-exa-openapi.ipynb)                 |

## 前提条件

在开始动手实验之前，请确保您具备以下条件：

- 具有 Bedrock AgentCore 及相关服务适当权限的 **AWS 账户**
  - `BedrockAgentCoreFullAccess` 托管策略
  - `AmazonBedrockFullAccess` 托管策略
  - `CloudWatchFullAccessV2` 托管策略 
  - `调用者权限`：请参阅详细策略 [此处](https://github.com/aws/bedrock-agentcore-starter-toolkit/blob/main/documentation/docs/user-guide/runtime/permissions.md#developercaller-permissions)
- ~~在 Bedrock 中申请 [Amazon Nova Pro 模型访问权限](https://docs.aws.amazon.com/nova/latest/userguide/getting-started-console.html)~~
- 为 AgentCore 可观测性[启用 CloudWatch Transaction Search](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/observability-configure.html#observability-configure-builtin)
- 已配置的 **AWS 凭证**（IAM 角色或环境变量） 
- 带有所需软件包的 **Python 环境**（在 `pyproject.toml` 和每个 notebook 的说明中列出）
- **Exa API Key**（Lab 3 和 Lab 7 需要）- 从 [Exa Dashboard](https://dashboard.exa.ai/api-keys) 获取

### AWS 区域

我们建议在本动手实验中使用 `us-east-1`。Bedrock AgentCore 在特定的 AWS 区域可用。请确保您在受支持的区域中工作。

### 环境设置

如果不使用 IAM 角色，请配置您的 AWS 凭证：

```python
import os

os.environ["AWS_ACCESS_KEY_ID"] = "<YOUR_ACCESS_KEY>"
os.environ["AWS_SECRET_ACCESS_KEY"] = "<YOUR_SECRET_KEY>"
os.environ["AWS_SESSION_TOKEN"] = "<OPTIONAL_SESSION_TOKEN>"
os.environ["AWS_REGION"] = "<AWS_REGION>"
```

## 动手实验结构

```
bedrock-agentcore-integration/workshop/cn/
├── 00-strands-agents/
│   └── 00-strands-agents-getting-started.ipynb
├── 01-bedrock-agentcore-code-interpreter/
│   └── 01-agentcore-code-interpreter.ipynb
├── 02-bedrock-agentcore-browser/
│   └── 02-agentcore-browser-use.ipynb
├── 03-bedrock-agentcore-identity-apikey/
│   └── 03-agentcore-identity-for-exa-mcp.ipynb
├── 04-bedrock-agentcore-runtime-mcp/
│   ├── 04-agentcore-runtime-for-mcp-deploy.ipynb
├── 05-bedrock-agentcore-runtime-and-observability/
│   ├── 05-agentcore-runtime-for-strands-deploy.ipynb
├── 06-bedrock-agentcore-memory/
│   ├── 06-agentcore-memory.ipynb
├── 07-bedrock-agentcore-gateway-openapi/
│   ├── 07-agentcore-gateway-for-exa-openapi.ipynb
│   └── exa-openapi-spec.yaml
├── pyproject.toml
├── uv.lock
└── README.md
```

## 快速开始

1. **设置您的 AWS 凭证**并确保您在受支持的区域中
2. 使用 **uv** 设置动手实验环境 - [安装 uv](https://docs.astral.sh/uv/getting-started/installation/)
   ```bash
   uv sync
   ```
3. **从 Lab 0 开始**，按顺序完成各个实验
4. **完成每个实验**后清理 AWS 资源 

> **注意：** 请确保清理动手实验期间创建的 AWS 资源，以避免不必要的费用。每个实验在适用的情况下都包含清理说明。

## 关键学习成果

完成本动手实验后，您将能够：

- 了解 Strands Agents 的基础知识和框架
- 构建具有代码执行功能的 AI 智能体
- 实现用于网页交互的浏览器自动化
- 安全地管理外部服务集成的凭证
- 在生产环境中部署和扩展 MCP 服务器
- 创建具有可观测性的综合智能体解决方案
- 集成持久化记忆功能以实现对话连续性
- 使用 Gateway 从 OpenAPI 规范生成 MCP 服务器
- 应用智能体开发和部署的最佳实践

## 支持与资源

- [Amazon Bedrock AgentCore 开发者指南](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/)
- [Amazon Bedrock AgentCore 示例](https://github.com/awslabs/amazon-bedrock-agentcore-samples)
- [Strands Agents SDK](https://strandsagents.com/latest/)
- [Strands Agents 示例](https://github.com/strands-agents/samples)
- [Amazon Bedrock 用户指南](https://docs.aws.amazon.com/bedrock/latest/userguide/)
- [Amazon Nova 用户指南](https://docs.aws.amazon.com/nova/latest/userguide/)

# GitHub MCP 配置流程

## 1. 安装GitHub MCP Server
```bash
npx -y @modelcontextprotocol/server-github
```

## 2. 获取GitHub Personal Access Token
1. 登录GitHub
2. 进入Settings -> Developer settings -> Personal access tokens
3. 点击Generate new token
4. 选择以下权限：
   - repo (全部权限)
   - workflow
5. 生成并复制token

## 3. 配置MCP Settings
编辑`cline_mcp_settings.json`，添加GitHub MCP配置：
```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your_personal_access_token"
      },
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

## 4. 验证配置
1. 重启VSCode
2. 检查MCP服务器是否正常运行
3. 测试GitHub API调用

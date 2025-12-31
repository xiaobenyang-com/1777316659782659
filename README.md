# 电影搜索工具 Search Movie

一个基于 Model Context Protocol (MCP) 构建的智能电影和电视剧资源搜索工具，支持多源搜索和链接验证。
An intelligent movie and TV series resource search tool based on Model Context Protocol (MCP), supporting multi-source search and link verification.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| search_movie | 搜索电影或电视剧资源。返回未验证的搜索结果列表，包含标题、链接和质量信息。使用此工具获取候选资源后，请从结果中选择最匹配的链接，然后使用 validate_video_url 工具验证其可播放性。 |
| validate_video_url | 验证特定视频链接的可播放性。接收一个视频播放页面的 URL 或 URL 数组，返回该链接是否可以正常播放。支持批量验证多个链接。只有通过验证的链接才能确保用户可以观看。 |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659782659](https://mcp.xiaobenyang.com/inspector/1777316659782659)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659782659](https://mcp.xiaobenyang.com/inspector/1777316659782659)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "电影搜索工具": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659782659/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "电影搜索工具": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659782659/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "电影搜索工具": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659782659",
          },
          "transport": "stdio"
        }
      }
}

```

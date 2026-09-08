На рабочем компьютере без npm

Нужен установленный или распакованный Node.js. В текущем package.json проекта указано требование Node.js ≥ 22; точка запуска — bin/mcp-abap-adt.js. Исходный package.json

Проверка запуска:

node "C:\Tools\abap-mcp\node_modules\@mcp-abap-adt\core\bin\mcp-abap-adt.js" --help

3. Подключение к Cline

В настройках MCP укажите прямой запуск через Node.js:

{
  "mcpServers": {
    "abap": {
      "command": "node",
      "args": [
        "C:/Tools/abap-mcp/node_modules/@mcp-abap-adt/core/bin/mcp-abap-adt.js",
        "--transport=stdio",
        "--env-path=C:/Tools/abap-mcp/sap.env"
      ],
      "disabled": false,
      "autoApprove": []
    }
  }
}

В sap.env задайте параметры вашей системы:

SAP_URL=https://your-sap-host:port
SAP_CLIENT=100
SAP_AUTH_TYPE=basic
SAP_USERNAME=your-user
SAP_PASSWORD=your-password

Замените адрес, порт и мандант своими значениями. Этот способ загрузки .env предусмотрен сервером. Документация запуска
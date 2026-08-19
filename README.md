# Senler.io Project Codex plugin

Плагин подключает Codex к проектному MCP-серверу Senler.io. После native OAuth он работает только с проектом и правами, выбранными при авторизации.

## Установка

Добавьте публичный marketplace:

```bash
codex plugin marketplace add https://github.com/SenlerBot/senler-io-codex-plugin.git
```

Установите плагин:

```bash
codex plugin add senler-io@senler
```

После установки откройте новую задачу Codex и вызовите любой защищённый инструмент. MCP-клиент сам запустит OAuth. Для выбора другого проекта переподключите сервер в настройках MCP-клиента.

## Возможности

- поиск и чтение документации Senler.io;
- просмотр данных подключённого проекта;
- работа с участниками, каналами, агентами, диалогами, пространствами и лидами;
- аналитика, источники данных, процессы, события, хранилище и переменные проекта;
- создание и изменение объектов в рамках OAuth-разрешений пользователя.
- просмотр текущего OAuth-подключения и выбранного проекта;
- интерактивная карточка проекта в клиентах с поддержкой MCP Apps и текстовый ответ в остальных клиентах.

Плагин не запрашивает токены в чате и не использует `OPENAI_API_KEY`. Авторизацией управляет MCP-клиент по стандартному OAuth.

## Обновление

```bash
codex plugin marketplace upgrade senler
codex plugin add senler-io@senler
```

После обновления откройте новую задачу Codex.

## Состав

- `.agents/plugins/marketplace.json` — публичный каталог;
- `plugins/senler-io/.codex-plugin/plugin.json` — manifest плагина;
- `plugins/senler-io/.mcp.json` — подключение к hosted MCP server;
- `plugins/senler-io/skills/senler-io/SKILL.md` — правила безопасной работы с Senler.io.

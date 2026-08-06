# Senler.io Codex plugin

Плагин подключает Codex к Senler.io через hosted MCP server. После OAuth-авторизации он работает только с тем проектом Senler.io и теми правами, которые выбрал пользователь.

## Установка

Добавьте публичный marketplace:

```bash
codex plugin marketplace add https://github.com/SenlerBot/senler-io-codex-plugin.git
```

Установите плагин:

```bash
codex plugin add senler-io@senler
```

После установки откройте новую задачу Codex и попросите подключить Senler.io. При первом использовании откроется OAuth-авторизация.

## Возможности

- поиск и чтение документации Senler.io;
- просмотр данных подключённого проекта;
- работа с участниками, каналами, агентами, диалогами, пространствами и лидами;
- аналитика, источники данных, процессы, события, хранилище и переменные проекта;
- создание и изменение объектов в рамках OAuth-разрешений пользователя.

Плагин не запрашивает токены в чате и не использует `OPENAI_API_KEY`. Для действий с Senler.io применяется OAuth.

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

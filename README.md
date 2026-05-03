# Telegram

Telegram is a cloud-based instant messaging and voice-over-IP service with a comprehensive Bot API for developers. Bots can send and receive messages, manage chats, handle payments, work with stickers, and integrate with any external service. The platform supports over 900 million users worldwide.

**Human URL:** [https://telegram.org](https://telegram.org)
**Developer URL:** [https://core.telegram.org](https://core.telegram.org)

## APIs

### Telegram Bot API (v9.5)
HTTP-based interface for building Telegram bots. All methods use HTTPS POST requests to `https://api.telegram.org/bot{token}/METHOD_NAME`.

- **Documentation:** [https://core.telegram.org/bots/api](https://core.telegram.org/bots/api)
- **Getting Started:** [https://core.telegram.org/bots](https://core.telegram.org/bots)
- **Changelog:** [https://core.telegram.org/bots/api-changelog](https://core.telegram.org/bots/api-changelog)
- **OpenAPI Spec:** [openapi/telegram-bot-openapi.yml](openapi/telegram-bot-openapi.yml)

**Key capabilities:** Receive updates (long polling or webhooks), send text/photos/documents/audio/video/voice/locations/contacts/polls, manage chats and members, handle payments with Telegram Stars, create sticker sets, and set bot command menus.

### Telegram TDLib
Cross-platform Telegram client library for building full-featured Telegram apps with MTProto.

- **Documentation:** [https://core.telegram.org/tdlib](https://core.telegram.org/tdlib)
- **GitHub:** [https://github.com/tdlib/td](https://github.com/tdlib/td)

## Artifacts

### OpenAPI Specifications
| File | Description |
|---|---|
| [openapi/telegram-bot-openapi.yml](openapi/telegram-bot-openapi.yml) | Telegram Bot API v9.5 — 40+ methods covering messaging, chat management, members, payments, stickers |

### JSON Schemas
| File | Description |
|---|---|
| [json-schema/telegram-message-schema.json](json-schema/telegram-message-schema.json) | Telegram Message object JSON Schema |
| [json-schema/telegram-update-schema.json](json-schema/telegram-update-schema.json) | Telegram Update object JSON Schema |

### JSON Structure
| File | Description |
|---|---|
| [json-structure/telegram-message-structure.json](json-structure/telegram-message-structure.json) | Telegram Message field structure documentation |

### JSON-LD
| File | Description |
|---|---|
| [json-ld/telegram-context.jsonld](json-ld/telegram-context.jsonld) | JSON-LD context mapping Telegram types to schema.org |

### Examples
| File | Description |
|---|---|
| [examples/telegram-send-message-example.json](examples/telegram-send-message-example.json) | sendMessage request/response example |
| [examples/telegram-get-updates-example.json](examples/telegram-get-updates-example.json) | getUpdates long polling example |
| [examples/telegram-send-poll-example.json](examples/telegram-send-poll-example.json) | sendPoll request/response example |

### Spectral Rules
| File | Description |
|---|---|
| [rules/telegram-bot-rules.yml](rules/telegram-bot-rules.yml) | Spectral ruleset enforcing Telegram Bot API conventions |

### Naftiko Capabilities
| File | Description |
|---|---|
| [capabilities/shared/telegram-bot.yaml](capabilities/shared/telegram-bot.yaml) | Shared Telegram Bot API capability definition |
| [capabilities/bot-messaging.yaml](capabilities/bot-messaging.yaml) | Bot messaging workflow (REST port 8080, MCP port 9090) |

### Vocabulary
| File | Description |
|---|---|
| [vocabulary/telegram-vocabulary.yml](vocabulary/telegram-vocabulary.yml) | Telegram platform vocabulary — 50+ terms across messaging, bots, payments, admin |

## Common Properties

| Property | URL |
|---|---|
| Developer Portal | https://core.telegram.org |
| Authentication | https://core.telegram.org/bots/api#authorizing-your-bot |
| Terms of Service | https://telegram.org/tos |
| Privacy Policy | https://telegram.org/privacy |
| Blog | https://telegram.org/blog |
| GitHub | https://github.com/tdlib |

## Maintainers
- **Kin Lane** — kin@apievangelist.com

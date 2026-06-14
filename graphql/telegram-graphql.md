# Telegram GraphQL Schema

A conceptual GraphQL schema for the Telegram Bot API, derived from the official
[Telegram Bot API reference](https://core.telegram.org/bots/api) (v9.5) and the
[TDLib](https://core.telegram.org/tdlib) type system.

## Overview

The schema covers every major object category in the Telegram Bot API:

| Category | Types |
|---|---|
| Root operations | Query, Mutation, Subscription |
| Updates | Update, ChatMemberUpdated |
| Messages | Message, MessageText, MessagePhoto, MessageVideo, MessageDocument, MessageAudio, MessageVoice, MessageVideoNote, MessageSticker, MessageAnimation, MessageContact, MessageLocation, MessagePoll, MessageDice, MessageEntity |
| Forward origins | MessageOrigin (interface), ForwardOrigin (union), ForwardOriginUser, ForwardOriginHiddenUser, ForwardOriginChat, ForwardOriginChannel |
| Chats | Chat, ChatType, ChatMember, ChatMemberStatus, ChatPermissions, ChatPhoto, ChatInviteLink, ChatLocation |
| Users | User, UserFullInfo, ProfilePhoto |
| Bot | BotCommand, BotDescription, BotShortDescription |
| Inline queries | InlineQuery, InlineQueryResult (interface), InlineQueryResultArticle, InlineQueryResultPhoto, ChosenInlineResult |
| Queries / callbacks | CallbackQuery, ShippingQuery, PreCheckoutQuery |
| Media | File, Animation, Audio, Document, PhotoSize, Video, VideoNote, Voice, Sticker, StickerSet, MaskPosition |
| Location & contact | Location, Venue, Contact |
| Keyboards | KeyboardButton, KeyboardButtonPollType, InlineKeyboardButton, ReplyKeyboardMarkup, InlineKeyboardMarkup, WebAppInfo, LoginUrl |
| Polls | Poll, PollOption, PollAnswer |
| Payments | Invoice, ShippingAddress, OrderInfo, LabeledPrice, SuccessfulPayment |
| Webhooks | WebhookInfo |
| Passport | PassportData, EncryptedPassportElement, PassportFile, EncryptedCredentials |

Total named types: **70+**

## Schema file

[telegram-schema.graphql](telegram-schema.graphql)

## Source APIs

- **Telegram Bot API** — REST HTTP interface for building Telegram bots.
  - Docs: <https://core.telegram.org/bots/api>
  - Base URL: `https://api.telegram.org/bot{token}`
  - GitHub: <https://github.com/tdlib/telegram-bot-api>

- **TDLib** — Native C++ Telegram client library used by official clients.
  - Docs: <https://core.telegram.org/tdlib>
  - GitHub: <https://github.com/tdlib/td>

## Design notes

- The schema is **conceptual**: Telegram's native transport is REST (Bot API)
  or MTProto binary (TDLib). This schema maps those types into GraphQL idioms so
  they can be consumed by GraphQL tooling, code generators, or gateway layers.
- `Query` fields mirror read operations (getMe, getChat, getFile, getWebhookInfo).
- `Mutation` fields mirror write/action Bot API methods (sendMessage, sendPhoto, etc.).
- `Subscription` provides an `updates` field for real-time event streaming,
  analogous to webhook delivery or long-polling.
- `MessageOrigin` is modelled as a **GraphQL interface** with a union alias
  (`ForwardOrigin`) so resolvers can return any concrete origin variant.
- `InlineQueryResult` is an **interface** to allow the various result subtypes
  (Article, Photo, etc.) to be returned from a single list field.
- The `JSON` scalar covers opaque structures (replyMarkup inputs, game objects)
  that do not have a fixed schema in the Telegram spec.

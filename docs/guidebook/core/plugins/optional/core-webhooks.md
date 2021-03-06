---
title: "Webhooks"
---

# Webhooks

::: tip
You can find the source code of this package at [packages/core-webhooks](https://github.com/ArkEcosystem/core/tree/develop/packages/core-webhooks).
:::

## Installation

```bash
yarn add @arkecosystem/core-webhooks
```

## Configuration

```js
module.exports = {
  enabled: process.env.ARK_WEBHOOKS_ENABLED,
  database: {
    dialect: 'sqlite',
    storage: `${process.env.ARK_PATH_DATA}/database/webhooks.sqlite`,
    logging: process.env.ARK_DB_LOGGING,
  },
  server: {
    enabled: process.env.ARK_WEBHOOKS_API_ENABLED,
    host: process.env.ARK_WEBHOOKS_HOST || '0.0.0.0',
    port: process.env.ARK_WEBHOOKS_PORT || 4004,
    whitelist: ['127.0.0.1', '::ffff:127.0.0.1'],
    pagination: {
      limit: 100,
      include: ['/api/webhooks'],
    },
  },
}
```

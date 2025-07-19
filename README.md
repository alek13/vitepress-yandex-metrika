[![vitepress-yandex-metrika](https://raw.githubusercontent.com/hywax/vitepress-yandex-metrika/main/.github/static/cover.png)](https://github.com/hywax/vitepress-yandex-metrika)

# VitePress Yandex Metrika

[![npm version][npm-version-src]][npm-version-href]
[![npm downloads][npm-downloads-src]][npm-downloads-href]
[![License][license-src]][license-href]

**Русский** | [English](./README.en.md)

Плагин для VitePress для отслеживания статистики Яндекс Метрики.

<details>
  <summary><b>Оглавление</b></summary>

* [Особенности](#-особенности)
* [Установка](#-установка)
* [Использование](#-использование)
  * [Подключение](#-подключение)
  * [Конфигурация](#-конфигурация)
* [Вкладчики](#-вкладчики)
* [Лицензия](#-лицензия)
</details>

## 🎯 Особенности

* 📊 Поддержка нескольких счетчиков
* ✨ Корректная работа с SPA приложениями
* ✅ Поддержка всех настроек метрики
* 🌐 Возможность использовать CDN для счетчиков
* 0️⃣ 0 зависимостей
* 🪄️ Поддержка TypeScript

## ✨ Установка

```shell
# Использование pnpm
pnpm add @hywax/vitepress-yandex-metrika -D

# Использование yarn
yarn add @hywax/vitepress-yandex-metrika -D

# Использование npm
npm install @hywax/vitepress-yandex-metrika -D
```

## ⚡ Использование

### 🚀 Подключение

Добавьте `yandexMetrika` в раздел темы `enhanceApp` в `index.ts`.

```typescript
// .vitepress/theme/index.ts
import type { Theme } from 'vitepress'
import { yandexMetrika } from '@hywax/vitepress-yandex-metrika'
import DefaultTheme from 'vitepress/theme'

export default {
  extends: DefaultTheme,
  enhanceApp({ router }) {
    yandexMetrika(router, {
      counter: {
        id: 12345678
      },
    })
  },
} satisfies Theme
```

### ⚙️ Конфигурация

Вы можете настроить плагин `yandexMetrika`, передав необходимые параметры в объект настроек.

```typescript
export interface YandexMetrikaOptions {
  enabled?: boolean // по умолчанию: true
  counter: YandexMetrikaCounter | YandexMetrikaCounter[]
  cdn?: {
    tag?: string // по умолчанию: https://mc.yandex.ru/metrika/tag.js
    watch?: string // по умолчанию: https://mc.yandex.ru/watch
  }
}

export interface YandexMetrikaCounter {
  id: number
  initParams?: {
    defer?: boolean // по умолчанию: false
    clickmap?: boolean // по умолчанию: true
    trackLinks?: boolean // по умолчанию: true
    accurateTrackBounce?: boolean // по умолчанию: true
    webvisor?: boolean // по умолчанию: false
    ecommerce?: boolean | string | Array<string | boolean> // по умолчанию: false
    trustedDomains?: string[] // по умолчанию: -
    childIframe?: boolean // по умолчанию: false
    type?: number // по умолчанию: 0
    triggerEvent?: boolean // по умолчанию: false
  }
}
```

Дополнительную информацию можно найти на [странице документации](https://yandex.ru/support/metrica/code/counter-initialize.html).

## 🏆 Вкладчики

Огромное спасибо всем, кто помогает улучшать проект. Благодаря вам проект может развиваться!

<img src="https://raw.githubusercontent.com/hywax/vitepress-yandex-metrika/main/.github/static/contributors.svg" alt="VitePress Yandex Metrika Вкладчики" width="100%"/>

## 📄 Лицензия

Основой VitePress Yandex Metrika являет открытый исходный код, в соответствии [MIT License](LICENSE).

<!-- Badges -->

[npm-version-src]: https://img.shields.io/npm/v/@hywax/vitepress-yandex-metrika/latest.svg?logo=hackthebox&color=4A4DFF&logoColor=fff
[npm-version-href]: https://npmjs.com/package/@hywax/vitepress-yandex-metrika
[npm-downloads-src]: https://img.shields.io/npm/dm/@hywax/vitepress-yandex-metrika.svg?colorB=4A4DFF
[npm-downloads-href]: https://npmjs.com/package/@hywax/vitepress-yandex-metrika
[license-src]: https://img.shields.io/badge/License-MIT-4A4DFF?logo=opensourceinitiative&logoColor=fff
[license-href]: https://npmjs.com/package/@hywax/vitepress-yandex-metrika

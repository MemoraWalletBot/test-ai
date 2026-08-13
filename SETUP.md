# 🛡️ Crypto Guardian AI — Инструкция по запуску

## Всё бесплатно:
| Сервис | Цена | Для чего |
|---|---|---|
| GitHub Pages | FREE | Хостинг Mini App |
| Telegram Bot API | FREE | Бот + Mini App |
| CoinGecko API | FREE | Данные рынка |
| Anthropic API | $5 кредитов (старт) | ИИ-ответы |

---

## Шаг 1 — GitHub Pages (хостинг)

1. Зайти на **github.com** → New repository
2. Назвать: `crypto-guardian-app`
3. Сделать **Public**
4. Загрузить `index.html` в репозиторий
5. Перейти: Settings → Pages → Source: **main branch**
6. Ваш URL: `https://ВАШ_НИК.github.io/crypto-guardian-app/`

---

## Шаг 2 — Создать Telegram бота

1. Написать **@BotFather** в Telegram
2. Команда: `/newbot`
3. Дать имя: `Crypto Guardian AI`
4. Дать юзернейм: `CryptoGuardianAI_bot`
5. Сохранить **токен бота** (он понадобится)

---

## Шаг 3 — Подключить Mini App к боту

В @BotFather:
```
/newapp
→ выбрать вашего бота
→ Title: Crypto Guardian AI
→ Description: ИИ-страж криптовалют
→ Web App URL: https://ВАШ_НИК.github.io/crypto-guardian-app/
```

Или через:
```
/mybots → ваш бот → Bot Settings → Menu Button → Edit Menu Button URL
→ вставить ваш GitHub Pages URL
```

---

## Шаг 4 — Anthropic API ключ

1. Зайти на **console.anthropic.com**
2. Зарегистрироваться
3. API Keys → Create Key
4. Скопировать ключ

**Добавить в index.html:**
Найти строку:
```javascript
headers: { 'Content-Type': 'application/json' },
```
Заменить на:
```javascript
headers: { 
  'Content-Type': 'application/json',
  'x-api-key': 'sk-ant-ВАШ_КЛЮЧ_ЗДЕСЬ',
  'anthropic-version': '2023-06-01'
},
```

> ⚠️ Для продакшена — перенести API ключ на backend (Node.js/Python), 
> чтобы не светить его в HTML!

---

## Функции приложения

### 💬 ИИ Чат
- Отвечает на любые вопросы о крипте на любом языке
- Анализирует коины по запросу
- Объясняет риски и токеномику
- Быстрые кнопки для частых вопросов

### 🔍 Скан (Скам-детектор)
- Анализ любого коина/мем-токена через ИИ
- Оценки: Безопасность, Ликвидность, Сообщество, Децентрализация
- Красные/зелёные флаги
- Вердикт на русском

### 📈 Рынок
- Реальные цены с CoinGecko (бесплатно, без ключа)
- Топ мем-коины: BONK, PEPE, WIF, SHIB и другие
- Топ крипто: BTC, ETH, SOL и другие
- Клик на коин → спросить ИИ о нём

### 👁️ Кошельки
- Добавление Solana кошельков для отслеживания
- История транзакций (mock данные, подключи Solana RPC для реальных)
- Хранение в localStorage браузера

---

## Улучшения (следующий этап)

- [ ] Backend на Node.js (скрыть API ключ)
- [ ] Реальный трекинг Solana кошельков через Helius API (бесплатный tier)
- [ ] Push-уведомления через Telegram Bot API
- [ ] Webhook для автоматических алертов
- [ ] База данных (Supabase free tier)

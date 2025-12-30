<div align="center">

# 🤖 Telegram AI Image Generator Bot

[![n8n](https://img.shields.io/badge/n8n->=1.0-black?style=flat-square&logo=n8n)](https://n8n.io/)

**Telegram-бот с поддержкой AI: отвечает на сообщения через LLM (OpenRouter) и генерирует изображения по запросу (Stability AI)**

</div>

---

## 📋 Описание

Бот выполняет две основные функции:

1. **AI-чат** — отвечает на сообщения, используя GPT через OpenRouter. Поддерживает множество языков и учитывает языковые предпочтения пользователя.

2. **Генерация изображений** — создаёт изображения по текстовому описанию с помощью Stable Diffusion XL от Stability AI.

### Ключевые команды

| Команда | Описание |
|---------|----------|
| `/start` | Запуск бота и приветствие |
| `/image <описание>` | Генерация изображения по описанию |

---

## 🛠 Технологии

- **n8n** — платформа автоматизации
- **Telegram Bot API** — взаимодействие с Telegram
- **OpenRouter** — API для доступа к LLM (GPT)
- **Stability AI** — генерация изображений (Stable Diffusion XL)

---

## 📦 Установка

### 1. Клонируйте репозиторий

```bash
git clone https://github.com/your-username/generator4yrpics_bot.git
cd generator4yrpics_bot
```

### 2. Настройте переменные окружения

```bash
cp .env.example .env
# Отредактируйте .env и добавьте ваши API-ключи
```

### 3. Импортируйте workflow в n8n

1. Откройте ваш n8n instance
2. Перейдите в Settings → Import
3. Загрузите файл workflow.json
4. Создайте credentials в n8n:
   - Telegram Api — для Telegram
   - OpenRouter Api — для OpenRouter
   - Bearer Auth — для Stability AI

### 4. Настройте Webhook

После импорта workflow:
- Скопируйте webhook URL из узла Telegram Trigger
- Настройте webhook в BotFather: /setwebhook

---

## 📁 Структура проекта
```
generator4yrpics_bot/
├── .gitignore           # Исключение чувствительных файлов
├── .env.example         # Шаблон переменных окружения
├── README.md            # Документация
├── workflow.json        # n8n workflow
└── docs/
    └── images/          # Скриншоты и медиа
```

## 📸 Скриншоты

### Workflow в n8n
![Workflow](docs/images/n8n-workflow.png)

### Пример генерации изображений
![Генерация](docs/images/image-generation-1.png)

![Генерация](docs/images/image-generation-2.png)

## 🔧 Workflow Overview
```
Telegram Trigger → PreProcessing → Settings → Send Chat Action
                                              ↓
                              Merge ←─────────────┘
                              ↓
                           Switch ───→ Basic LLM Chain → Send Text Message
                              ↓
                    HTTP Request → Base64 to PNG → Send Photo Message
```

## 🤝 Contributing

1. Forkните репозиторий
2. Создайте ветку (git checkout -b feature/amazing-feature)
3. Commitните изменения (git commit -m 'Add amazing feature')
4. Pushните в ветку (git push origin feature/amazing-feature)
5. Откройте Pull Request

## 📄 Лицензия

MIT License

## 🙏 Благодарности
- [n8n](https://n8n.io/) — за мощную платформу автоматизации
- [OpenRouter](https://openrouter.ai/) — за доступ к LLM
- [Stability AI](https://stability.ai/) — за генерацию изображений

---

## 📞 Контакты

**Автор**: Ivan P  
**Telegram**: [@nonoyessure](https://t.me/nonoyessure)

---

<div align="center">
  Сделано с ❤️
</div>

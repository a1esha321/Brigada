# Бригада

Учёт заказов и смен монтажной бригады: работы, суммы каждому, импорт плана
из 1С, отчёт для HR. Один файл `index.html`, работает как Telegram Mini App.

## Быстрый старт (один раз)

1. **GitHub.** Создай репозиторий `brigada`, загрузи эти файлы:
   ```bash
   git init && git add . && git commit -m "Бригада v2"
   git branch -M main
   git remote add origin https://github.com/ВАШ_ЛОГИН/brigada.git
   git push -u origin main
   ```
2. **GitHub Pages.** В репозитории: Settings → Pages → Source: Deploy from
   a branch → Branch: `main`, папка `/ (root)` → Save.
   Через минуту приложение доступно по адресу
   `https://ВАШ_ЛОГИН.github.io/brigada/`.
3. **Telegram.** В @BotFather: `/newbot` (имя и @username бота), затем
   `/newapp` → выбрать бота → название, описание, картинка →
   вставить URL из шага 2. Готово: приложение открывается в Telegram,
   данные хранятся в облаке Telegram.

## Обновления через Claude Code

Установка (нужен аккаунт Claude Pro/Max или Console):
```bash
npm install -g @anthropic-ai/claude-code
```

Рабочий цикл:
```bash
cd brigada
claude
```
Дальше — обычным языком, например:
> Добавь на вкладку Сводка кнопку «Скопировать сводку за месяц текстом»

> Сделай, чтобы при оформлении из плана участники прошлой работы
> этого заказа подставлялись автоматически

> Закоммить и запушь с понятным сообщением

Claude Code читает `CLAUDE.md`, знает правила проекта (формат отчёта HR,
один файл, хранилище) и умеет сам делать commit/push. После push
GitHub Pages обновляется за ~1–2 минуты — в Telegram сразу новая версия.

Документация: https://code.claude.com/docs/en/quickstart

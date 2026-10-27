# Лабораторная работа: Husky + ESLint + DeepSeek

Студент: Ван Кайбо. Дисциплина: Web-проектирование и web-дизайн.

## Проверка проекта

```sh
npm ci
npm run lint
node calc.js
```

В `.husky/pre-commit` запускается `npm run lint`. ESLint использует ES Modules,
JavaScript-конфигурацию, рекомендованные правила и глобальные переменные Browser
и Node. Функции `add`, `sub`, `mul`, `div` находятся в `calc.js`; деление на ноль
возвращает `null`.

## Проверка блокировки коммита

В исходном коде преподавателя вызов `summ(2, 3)` не имел определения. При
попытке коммита ESLint выдал `no-undef`, а Husky остановил коммит. После
исправления повторный коммит прошёл успешно. Исходные записи терминала:

- [`evidence/terminal/01-failed-commit.typescript`](evidence/terminal/01-failed-commit.typescript)
- [`evidence/terminal/02-successful-commit.typescript`](evidence/terminal/02-successful-commit.typescript)

Записи созданы утилитой `script` при фактическом запуске `git commit`. Это не
снимки экрана терминала; соответствующие скриншоты необходимо приложить отдельно.

## Три запроса к DeepSeek

1. Ролевой запрос: настройка и объяснение ESLint. [Скриншот](evidence/deepseek/01-role.png).
2. Zero-shot: генерация `.gitignore` без примера. [Скриншот](evidence/deepseek/02-zero-shot.png).
3. One-shot: настройка `pre-commit` по одному примеру. [Скриншот](evidence/deepseek/03-one-shot.png).

Ответы ИИ проверены запуском команд. Предложение не включать `package-lock.json`
в репозиторий отклонено: файл зафиксирован для воспроизводимой установки.
Секреты и приватные данные в запросы не отправлялись.

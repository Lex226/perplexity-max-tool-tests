# 🚀 Perplexity Max Tool Tests

Интерактивное пространство для систематического тестирования возможностей Perplexity Max.

[![Open in Browser](https://img.shields.io/badge/Open-Tool%20Tests%20App-20b2aa?style=for-the-badge)](https://htmlpreview.github.io/?https://raw.githubusercontent.com/Lex226/perplexity-max-tool-tests/main/tool-tests.html)

---

## Что внутри

В репозитории собрана базовая панель навигации, охватывающая 10 инструментов Perplexity Max:

### Режимы поиска
| Инструмент | Доступ | Описание |
|---|---|---|
| **Search Modes** | Free | Best, Pro Search — сравнение глубины поиска и качества результата |
| **Deep Research** | Pro+ | Agentic loop: 20–50+ поисковых итераций, reasoning, отчёт |
| **Reasoning Models** | Pro+ | o3-pro, Claude Opus 4 и другие модели для сложных задач |

### Генерация
| Инструмент | Доступ | Описание |
|---|---|---|
| **Labs (Create)** | Max Unlimited | Генерация Excel, HTML-приложений, презентаций |
| **Image Generation** | Pro+ | Генерация и редактирование изображений |

### Контекст и интеграции
| Инструмент | Доступ | Описание |
|---|---|---|
| **File Upload** | Pro+ | Анализ CSV, PDF, скриншотов и других файлов |
| **MCP Servers** | Max | GitHub, БД, файловая система и внешние интеграции |
| **Spaces** | Pro+ | Изолированные рабочие пространства с системным промптом |

### Max Exclusive
| Инструмент | Доступ | Описание |
|---|---|---|
| **Comet Browser** | Max Only | AI-нативная работа в браузере |
| **Agent API** | API | `sonar-deep-research` через REST и SDK |

---

## Структура репозитория

```text
perplexity-max-tool-tests/
├── README.md
├── docs/
│   └── session-snapshots/
│       └── 2026-07-08-session-snapshot.md
└── app/
    └── tool-tests.html
```

### Назначение файлов
- `README.md` — краткое описание проекта, возможностей и структуры.
- `app/tool-tests.html` — основное HTML-приложение для тестирования инструментов.
- `docs/session-snapshots/2026-07-08-session-snapshot.md` — снимок текущего состояния проекта и договорённостей.

---

## Как открыть приложение

### В браузере
Открой [preview-версию](https://htmlpreview.github.io/?https://raw.githubusercontent.com/Lex226/perplexity-max-tool-tests/main/app/tool-tests.html).

### Локально
```bash
git clone https://github.com/Lex226/perplexity-max-tool-tests
cd perplexity-max-tool-tests
open app/tool-tests.html
```

Если команда `open` недоступна, просто открой файл `app/tool-tests.html` через проводник или браузер.

---

## Что уже реализовано

- Готовые промпты под стек 1С + SQL Server + Medallion + Power BI.
- Чеклисты шагов тестирования для каждого инструмента.
- Переключение статуса: ⬜ → 🔶 → ✅.
- Заметки для каждого инструмента.
- Экспорт заметок в Markdown.
- Прогресс-бар по прохождению тестов.
- Светлая и тёмная темы.

---

## Идеи для следующих шагов

- Подключить GitHub Pages.
- Добавить отдельные markdown-страницы с кейсами.
- Вынести пользовательские промпты в JSON или YAML.
- Добавить changelog.
- Добавить каталог примеров для MCP-сценариев.

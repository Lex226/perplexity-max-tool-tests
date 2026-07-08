# 📸 Session Snapshot — 2026-07-08

> Сохранено: среда, 8 июля 2026, ~13:09 MSK  
> Тред: «Как работает Deep Research в Perplexity Max»

---

## 🧵 О чём был тред

Тред начался с технического вопроса про Deep Research в Perplexity Max. Прошли три этапа:

1. **Deep Research deep-dive** — разобрали архитектуру изнутри (ReAct loop, sonar-deep-research модель, Agent API)
2. **Tool Tests Space** — создали интерактивное веб-приложение для тестирования инструментов
3. **GitHub репозиторий** — создали этот репо и загрузили README + снапшот

---

## 🔬 Ключевые находки: Deep Research

### Архитектура
- **Модель:** `sonar-deep-research` (base: DeepSeek R1 для reasoning)
- **Паттерн:** ReAct loop (Reason + Act) — итеративный agentic цикл
- **Цикл:** `Goal → Plan → [Search → Read → Reason → Re-plan]* → Synthesize → Report`
- **Context window:** 128K токенов — вся история поиска в памяти

### Инструменты модели
| Tool | Что делает |
|---|---|
| `web_search` | Поиск с фильтрами по доменам, датам, языку |
| `fetch_url` | Полный fetch содержимого страницы (не сниппет) |

### Метрики одного запроса (из документации)
```text
num_search_queries:  21
reasoning_tokens:    193 947
completion_tokens:   11 395
citation_tokens:     19 028
```

### 4 фазы работы
1. **Contextual Priming** — парсинг запроса, начальный research plan
2. **Adaptive Crawling** — итеративный поиск, каждый запрос строится на предыдущем
3. **Cross-Validation Loops** — поиск противоречий между источниками
4. **Dynamic Replanning** — если ответ не найден, перестройка плана

### Бенчмарки
- **Humanity's Last Exam:** 21.1% (выше Gemini Thinking, o3-mini, o1, DeepSeek-R1)
- **SimpleQA:** 93.9% accuracy

### Agent API (июнь 2026)
```python
from perplexity import Perplexity
client = Perplexity()
response = client.responses.create(
    preset="medium",  # или "advanced-deep-research"
    input="Твой вопрос..."
)
```

### Pro Search vs Deep Research
| | Pro Search | Deep Research |
|---|---|---|
| Итераций поиска | 3–5 | 20–50+ |
| Время | ~5 сек | 2–4 мин |
| Reasoning | Нет | 193K+ токенов |
| Модель | `sonar-pro` | `sonar-deep-research` |
| Стоимость | Стандарт | $3/M reasoning + $5/1K queries |

---

## 🧪 Tool Tests Space — что сделано

### Приложение
- **Файл:** `app/tool-tests.html` (86KB, vanilla HTML/CSS/JS)
- **Стек:** Geist Font + Lucide Icons, без зависимостей, без build step
- **Темы:** светлая + тёмная (system preference + toggle)

### Покрытые инструменты (10 штук)

#### Режимы поиска
| Инструмент | Доступ |
|---|---|
| Search Modes (Best/Pro) | Free |
| Deep Research | Pro+ |
| Reasoning Models (o3-pro, Claude Opus 4) | Pro+ |

#### Генерация
| Инструмент | Доступ |
|---|---|
| Labs (Create) — Excel, HTML-app, Slides | Max Unlimited |
| Image Generation | Pro+ |

#### Контекст и интеграции
| Инструмент | Доступ |
|---|---|
| File Upload (CSV, PDF, screenshots) | Pro+ |
| MCP Servers (GitHub, БД, файловая система) | Max |
| Spaces (системный промпт, изоляция) | Pro+ |

#### Max Exclusive
| Инструмент | Доступ |
|---|---|
| Comet Browser | Max Only |
| Agent API (`sonar-deep-research`) | API |

### Фичи приложения
- Готовые промпты под стек 1С + SQL Server + Medallion + Power BI
- Чеклист шагов тестирования для каждого инструмента
- Статус-переключатель: ⬜ → 🔶 → ✅ с dot-индикатором в сайдбаре
- Поле заметок per-tool
- Кнопка экспорта → `tool-tests-notes.md`
- Прогресс-бар в сайдбаре

---

## 📁 Структура репозитория

```text
perplexity-max-tool-tests/
├── README.md
├── docs/
│   └── session-snapshots/
│       └── 2026-07-08-session-snapshot.md
└── app/
    └── tool-tests.html
```

---

## 🔜 Что можно продолжить в новом треде

- [ ] Подключить GitHub Pages для репо.
- [ ] Пройтись по чеклисту инструментов в приложении.
- [ ] Добавить тесты для MCP Servers.
- [ ] Сравнить Comet Browser с обычным Deep Research.
- [ ] Попробовать Agent API с кастомными функциями для 1С/SQL Server данных.
- [ ] Расширить Space prompt под конкретные задачи BI/DWH.

---

## 👤 Контекст пользователя

- **Имя:** Alex Esco
- **Стек:** 1С ERP (Alfa-Auto), SQL Server, Power BI, Medallion Architecture
- **GitHub:** [@Lex226](https://github.com/Lex226)
- **Локация:** Amsterdam
- **Интересы в AI:** Data engineering автоматизация, CI/CD для аналитики, AI-assisted dev

---

*Снапшот создан автоматически через Perplexity AI + GitHub MCP*

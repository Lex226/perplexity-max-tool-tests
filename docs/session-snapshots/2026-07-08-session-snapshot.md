# 📸 Session Snapshot — 2026-07-08 (v2)

> Сохранено: среда, 8 июля 2026, ~14:10 MSK  
> Тред: «Настройка репозитория perplexity-max-tool-tests»

---

## 🧵 О чём был тред (v2)

Это продолжение треда v1. Главная цель: настроить репозиторий правильно. Пройдено два этапа:

1. **README fix** — обнаружена проблема кодировки (base64/битый UTF-8), заменён нормальным README
2. **Реорганизация структуры** — созданы директории `app/` и `docs/session-snapshots/`
3. **Draft PR #1** — открыт PR для мерджа изменений в `main`

---

## 📁 Текущее состояние репозитория

```text
perplexity-max-tool-tests/      (main branch)
├── README.md                      ← ещё старый (битый)
├── SESSION_SNAPSHOT.md           ← ещё в корне (v1)
└── tool-tests.html               ← ещё в корне (86KB)

perplexity-max-tool-tests/      (branch: chore/repo-structure-and-readme-fix)
├── README.md                      ← ✅ исправлен, нормальный UTF-8
├── tool-tests.html               ← ⚠️  заглушка (нужно перенести реальный HTML)
├── docs/
│   └── session-snapshots/
│       └── 2026-07-08-session-snapshot.md
└── app/
    ├── .gitkeep
    └── (нужно добавить tool-tests.html)
```

### Открытые PR
- **PR #1** — [`chore/repo-structure-and-readme-fix`](https://github.com/Lex226/perplexity-max-tool-tests/pull/1) → `main` | Draft

---

## ✅ Что сделано в этом треде

- [x] Обнаружена и исправлена проблема кодировки README (base64 вместо UTF-8)
- [x] Предложена и создана новая структура репо
- [x] Снапшот v1 перенесён в `docs/session-snapshots/`
- [x] Открыт draft PR #1

---

## 🔜 Что осталось до полного мерджа PR #1

- [ ] Перенести реальный HTML-контент из `tool-tests.html` в `app/tool-tests.html`
- [ ] Удалить заглушку в корне (или удалить файл целиком если оставить HTML в корне)
- [ ] Убрать `SESSION_SNAPSHOT.md` из корня (v1 уже есть в `docs/`)
- [ ] Перевести PR из Draft → Ready for Review и мерджить

---

## 💡 Идеи для следующих тредов

- **GitHub Pages** — подключить после мерджа (Settings → Pages → main → `/app` или `/`)
- **CHANGELOG.md** — добавить краткий changelog
- **MCP-сценарии** — папка `docs/mcp-scenarios/` с примерами GitHub MCP
- **Prompts JSON** — вынести пользовательские промпты в `app/prompts.json` для прощего редактирования
- **GitHub Pages badge** — добавить в README badge со ссылкой на live-приложение

---

## 🔬 Ключевые находки: Deep Research (из v1)

### Архитектура
- **Модель:** `sonar-deep-research` (base: DeepSeek R1 для reasoning)
- **Паттерн:** ReAct loop (Reason + Act) — итеративный agentic цикл
- **Цикл:** `Goal → Plan → [Search → Read → Reason → Re-plan]* → Synthesize → Report`
- **Context window:** 128K токенов

### Pro Search vs Deep Research
| | Pro Search | Deep Research |
|---|---|---|
| Итераций | 3–5 | 20–50+ |
| Время | ~5 сек | 2–4 мин |
| Reasoning | Нет | 193K+ токенов |
| Модель | `sonar-pro` | `sonar-deep-research` |

---

## 👤 Контекст пользователя

- **Имя:** Alex Esco
- **Стек:** 1С ERP (Alfa-Auto), SQL Server, Power BI, Medallion Architecture
- **GitHub:** [@Lex226](https://github.com/Lex226)
- **Интересы в AI:** Data engineering автоматизация, CI/CD для аналитики, AI-assisted dev

---

*Снапшот создан автоматически через Perplexity AI + GitHub MCP*

# РОДИННА КОВБАСКА — автоматичний звіт Bolt Food UA

Пакет для автооновлюваного звіту партнера **РОДИННА КОВБАСКА** (заклади «Родинна ковбаска»).
Побудований за методичкою [Stores-internal-weekly-report](https://github.com/mykhailobrynchak-dev/Stores-internal-weekly-report/tree/main/docs) (шаблон Hop Hey: вкладки Monthly + Weekly).

## Параметри звіту

| Параметр | Значення |
|----------|----------|
| `PARTNER_NAME` (group_name у Databricks) | `RODYNNA KOVBASKA` (32 заклади) |
| `PARTNER_DISPLAY` (заголовок) | `РОДИННА КОВБАСКА` |
| `DATA_START` | `2025-01-01` |
| Initials (лого) | `RK` |
| Slug публічного репо / Pages | `rodynna-kovbaska-report` |
| Live URL | https://khrystynaberezna-lgtm.github.io/rodynna-kovbaska-report/ |

## Файли

```
RODYNNA KOVBASKA/
├── generate_report.py                 # тягне дані з Databricks → index.html
├── template.html                      # HTML-шаблон (брендинг Bolt, Chart.js)
├── publish.sh                         # генерація + git push у публічний репо
├── requirements.txt                   # databricks-sql-connector
├── .env                               # конфіг + Databricks PAT (НЕ в git)
├── .env.example                       # шаблон конфігу
├── .gitignore                         # .env та report_data.json не комітяться
├── cursor-rule.mdc                    # правило Cursor для цього звіту
├── README.md                          # цей файл
└── .github/workflows/update-report.yml  # автооновлення щопонеділка 05:00 UTC
```

## Оновлення

- **Автоматично**: GitHub Actions щопонеділка о 05:00 UTC (08:00 Київ).
- **Вручну**: репо → Actions → «Оновлення звіту РОДИННА КОВБАСКА» → Run workflow.
- **Локально**: `cd "RODYNNA KOVBASKA" && ./publish.sh`.

> Databricks PAT живе 90 днів — після прострочення згенеруй новий і онови `.env`
> та секрет `DATABRICKS_TOKEN` у репо.

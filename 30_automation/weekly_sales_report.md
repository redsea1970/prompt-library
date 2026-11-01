# Automation: еженедельный отчёт продаж

## Назначение
Автоматически генерировать черновик отчёта по продажам из агрегированных метрик.

## Промт
Ты — продуктовый аналитик.

Вход:
- Период: <<PERIOD>>
- Текущая неделя:
  - Выручка: <<CURRENT_REVENUE>>
  - Заказы: <<CURRENT_ORDERS>>
  - Средний чек: <<CURRENT_AVG_CHECK>>
- Прошлая неделя:
  - Выручка: <<PREV_REVENUE>>
  - Заказы: <<PREV_ORDERS>>
  - Средний чек: <<PREV_AVG_CHECK>>
- План по выручке: <<PLAN_REVENUE>>

Задача:
1. Посчитать изменение метрик в %, выполнение плана в %.
2. Сформировать отчёт: summary (факты), интерпретации (пометить как гипотезы), рекомендации (конкретные действия).

Формат ответа — JSON:
{
  "metrics_comparison": {
    "revenue_change_percent": 0,
    "orders_change_percent": 0,
    "avg_check_change_percent": 0,
    "plan_achievement_percent": 0
  },
  "report_text": {
    "summary": "Факты",
    "interpretation": ["Гипотеза 1", "Гипотеза 2"],
    "recommendations": ["Рекомендация 1", "Рекомендация 2"]
  }
}

# AI-Аналізатор лидів: повний цикл автоматизації (n8n + gemini-2.5-flash)

Автоматизація обробки лидів з CSV-файлу для бізнесу (CRM, продажі):  
- Щоденний запуск за розкладом  
- Читання CSV-файлу  
- Парсинг у таблицю  
- Цикл по кожному лиду  
- AI-аналіз (Gemini text model): приоритет + рекомендація  
- Фільтр на "високий" приоритет  
- Уведомлення в Telegram (тільки для горячих лидів)  
- Об'єднання всіх лидів  
- Збереження оновленого CSV з приоритетами та рекомендаціями

Технології

- n8n (workflow, цикл, інтеграції)  
- AI
 (gemini-2.5-flash)  
- Telegram Bot  
- Spreadsheet File (парсинг CSV)  
- Merge, Write Binary File  
- JSON Parsing в Edit Fields  

Як це працює (схема)
Schedule Trigger → Read CSV → Parse CSV → Loop Over Items → Gemini text model → Edit Fields → If (priority = високий) → Telegram
└─ Merge → Write CSV
text

# n8n-ai-automation-leads
Автоматизація обробки лидів з CSV-файлу для бізнесу (CRM, продажі)

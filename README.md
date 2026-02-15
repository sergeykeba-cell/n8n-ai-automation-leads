# AI-Аналізатор лидів: повний цикл автоматизації (n8n + gemini-2.5-flash)

### Автоматизація обробки лидів з CSV-файлу для бізнесу (CRM, продажі):  
- Щоденний запуск за розкладом  
- Читання CSV-файлу  
- Парсинг у таблицю  
- Цикл по кожному лиду  
- AI-аналіз (Gemini text model): приоритет + рекомендація  
- Фільтр на "високий" приоритет  
- Уведомлення в Telegram (тільки для горячих лидів)  
- Об'єднання всіх лидів  
- Збереження оновленого CSV з приоритетами та рекомендаціями

### Технології

- n8n (workflow, цикл, інтеграції)  
- AI
 (gemini-2.5-flash)  
- Telegram Bot  
- Spreadsheet File (парсинг CSV)  
- Merge, Write Binary File  
- JSON Parsing в Edit Fields  

### Як це працює (схема)
Schedule Trigger → Read CSV → Parse CSV → Loop Over Items → Gemini text model → Edit Fields → If (priority = високий) → Telegram
└─ Merge → Write CSV

### Як запустити локально

1. Запусти n8n в Docker:
docker run -d 
--name n8n 
--restart unless-stopped 
-p 5678:5678 
-v ~/.n8n:/home/node/.n8n 
-v ~/n8n-files:/home/node/.n8n-files 
n8nio/n8n
text
2. Скопіюй leads.csv в ~/n8n-files
3. Відкрий http://localhost:5678 → імпортуй workflow (JSON нижче)
4. Заміни ключ Gemini і Telegram Chat ID
5. Execute Workflow → перевір Telegram і папку ~/n8n-files

### Як імпортувати

В n8n: Workflows → ... → Import from file → n8n-ai-automation-leads.json
Після імпорту:
Заміни ВАШ_API_КЛЮЧ_GEMINI на свій ключ (з https://aistudio.google.com/app/apikey)
Налаштуй Telegram credential і chat_id
Перевір шлях до файлу: /home/node/.n8n-files/leads.csv (якщо інший — зміни)

Execute Workflow — цикл пройде по всім рядкам, Gemini проаналізує кожен лід, Telegram відправить тільки про "високий", Merge збереже всі, Write — оновлений CSV.


---
id: local-ai-readme
type: guide
domain: ai_admin
status: active
created: 2026-02-17
updated: 2026-02-17
tags: [ai, local, gpt4all]
---



<div style="width:100%; max-width:700px; margin:0 auto 18px auto; border-radius: 18px; background: linear-gradient(90deg, #6366f1 0%, #06b6d4 100%); color: #fff; padding: 28px 18px 18px 18px; box-shadow: 0 2px 12px #0001; text-align:center;">
	<span style="font-size:2.5em;">🧠</span>
	<h1 style="margin: 0 0 8px 0; font-size:2em; font-weight:800; letter-spacing:1px; color:#fff;">Local AI (GPT4All) Integration</h1>
</div>

---

<div style="background: #fffbe6; border-radius: 12px; padding: 12px; margin-bottom: 16px;">
Руководство по запуску и использованию локальной LLM (<b>GPT4All</b>) для работы с Obsidian без затрат на OpenAI.
</div>

---

## ⚡ Быстрый старт
1. Подготовьте окружение:
	```powershell
	cd "<repo-root>"
	.\Interview-Prep\tools\install_local_ai.ps1
	```
2. Скачайте модель GPT4All и поместите в <code>Interview-Prep/models/</code> (см. <a href="https://gpt4all.io/models/">gpt4all.io/models/</a>)
3. Запустите сервер:
	```powershell
	Interview-Prep\tools\.venv\Scripts\python.exe Interview-Prep\tools\local_ai_server.py --model Interview-Prep/models/&lt;model-file&gt;
	```

---

## 📝 Пример использования
Вставить результат генерации в заметку через <b>QuickAdd</b> или терминал:
```powershell
$prompt = 'Explain the Java Memory Model in 3 short bullets.'
curl -X POST http://127.0.0.1:5000/generate -H "Content-Type: application/json" -d ("{\"prompt\": \"$prompt\"}")
```

---

## 💡 Примечания
- Модели могут быть большими, загрузка и запуск займут время
- Производительность зависит от вашего ПК
- Для быстрой настройки используйте <code>install_local_ai.ps1</code> и <code>local_ai_server.py</code>

---
_Используйте это руководство для автономной работы с AI в Obsidian._







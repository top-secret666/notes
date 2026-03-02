
---
id: automation-readme
type: guide
domain: ai_admin
status: active
created: 2026-02-17
updated: 2026-02-17
tags: [automation, ai, openai]
---



<div style="width:100%; max-width:700px; margin:0 auto 18px auto; border-radius: 18px; background: linear-gradient(90deg, #6366f1 0%, #06b6d4 100%); color: #fff; padding: 28px 18px 18px 18px; box-shadow: 0 2px 12px #0001; text-align:center;">
  <span style="font-size:2.5em;">🤖</span>
  <h1 style="margin: 0 0 8px 0; font-size:2em; font-weight:800; letter-spacing:1px; color:#fff;">Automation & OpenAI Setup</h1>
</div>

---

<div style="background: #e6f7ff; border-radius: 12px; padding: 12px; margin-bottom: 16px;">
Руководство по автоматизации и интеграции <b>OpenAI</b> и плагинов в Obsidian.
</div>

---

## 🚀 Быстрый старт
1. Откройте <b>PowerShell</b> в корне репозитория
2. Запустите:
	 ```powershell
	 .\bootstrap.ps1
	 ```
3. Если Python не установлен — скачайте с <a href="https://python.org">python.org</a>

---

## 🔑 OpenAI API Key
- Для плагинов: вставьте ключ в настройки плагина Obsidian
- Для скриптов: создайте файл <code>.env</code> с содержимым:
	```
	OPENAI_API_KEY=sk-...
	```

---

## 🛠️ GitHub Actions
- Автоматический запуск скриптов при пуше в <b>main</b>
- Для доступа к OpenAI добавьте секрет <b>OPENAI_API_KEY</b> в настройки репозитория

---

## 🧩 Плагины
- Копируйте плагины в <code>.obsidian/plugins</code>, отключите <b>Safe Mode</b> и включите нужные плагины

---

<div align="center" style="color: #888; font-size: 1.1em; margin-top: 18px;">
_Следуйте этому гайду для быстрой настройки автоматизации и AI-интеграции._
</div>







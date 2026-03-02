
<div align="center">
  <img src="https://images.unsplash.com/photo-1519125323398-675f0ddb6308?auto=format&fit=crop&w=600&q=80" alt="RGR Checklist" width="340" style="border-radius: 16px; margin-bottom: 12px;" />
  <h1>✅ RGR — подробный чеклист</h1>
</div>

---

<b>Цель:</b> сделать <code>rgr</code> reproducible и готовым для показа на интервью.

---

## ⚡ Quick wins (1–3 дня)
- [ ] README.md — краткое описание проекта (что делает, стек, структура репо, основные команды).
- [ ] Добавить <code>./README.md</code> секцию Quickstart с командой:
  - <code>docker compose --profile all up -d</code>
  - Как остановить: <code>docker compose down</code>.
- [ ] Создать <code>.env.example</code> с перечислением важных переменных (KEYCLOAK_ISSUER_URI, DB URL/USER/PASS, ports).
- [ ] В README добавить список портов и адресов сервисов (user, restaurant, order, keycloak).
- [ ] Добавить примеры curl для регистрации / логина / получения данных (три примера).

---

## 🧪 Инструменты и тесты (2–4 дня)
- [ ] Добавить один интеграционный тест для <code>user-service</code> (регистрация -> login -> получить профиль).
- [ ] Добавить один интеграционный тест для <code>restaurant-service</code> (создать ресторан -> получить список).
- [ ] Обновить <code>docker-compose.yml</code> healthchecks (для DB и сервисов) и указать их в README.

---

## 📄 Документация и отладка (1–2 дня)
- [ ] Описать в README, как настраивать Keycloak (realm import) или где взять тестовые credentials.
- [ ] Добавить секцию Troubleshooting: типичные ошибки (DB connection, Keycloak issuer mismatch) и как смотреть логи (<code>docker compose logs -f user-service</code>).
- [ ] Прописать команды сборки: <code>mvn -DskipTests -f user-service/pom.xml clean package</code> и как запускать сервисы локально.

---

## 🎬 Демо и презентация (1 день)
- [ ] Сделать short demo script (5 шагов) и записать 30–60s видео или gif: запустить docker compose → зарегистрировать пользователя → показать ответ API.
- [ ] В README добавить «What I did» — список твоих ролей и изменений в проекте (3–5 пунктов).

---

## 📅 Распределение по дням (пример)
- День 1: README quickstart + .env.example + порты
- День 2: Примеры curl + healthchecks в docker-compose
- День 3: Интеграционный тест для user-service
- День 4: Интеграционный тест для restaurant-service
- День 5: Troubleshooting + demo gif

---

## 📝 Как сдавать/фиксировать прогресс
- Создавай маленькие PR или коммиты с понятными сообщениями (например, <code>docs(rgr): add quickstart and .env.example</code>).
- В Obsidian добавляй ссылку на коммит в daily note.









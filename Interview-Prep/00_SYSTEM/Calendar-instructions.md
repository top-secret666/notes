

<div style="width:100%; max-width:700px; margin:0 auto 18px auto; border-radius: 18px; background: linear-gradient(90deg, #6366f1 0%, #06b6d4 100%); color: #fff; padding: 28px 18px 18px 18px; box-shadow: 0 2px 12px #0001; text-align:center;">
  <span style="font-size:2.5em;">🗓️</span>
  <h1 style="margin: 0 0 8px 0; font-size:2em; font-weight:800; letter-spacing:1px; color:#fff;">Make.md — Календарь уроков</h1>
</div>

---

> [!info] <b>Мы используем Make.md (плагин <code>make.md</code>) как единственный источник правды для календаря.</b>

**Цель:** показать уроки в календаре, планировать их и записывать дату в поле <code>planned_date</code> у каждой заметки-урока.

---

## 🚦 Как настроить (пошагово)

1️⃣ <b>Включите Make.md</b> (Settings → Community plugins) и откройте Navigator / Spaces.

2️⃣ <b>Создайте поле <code>planned_date</code> в ваших уроках (frontmatter).</b> Рекомендуемый формат: <code>YYYY-MM-DD</code>.
<br>Пример frontmatter:

```yaml
---
lesson_number: 2
planned_date: 2026-04-19
---
```

3️⃣ <b>Откройте Make.md → Spaces → Create Space → выберите папку <code>Interview-Prep/lessons</code></b>.
   - Добавьте View → Calendar View
   - Настройте поле даты: <code>planned_date</code>
   - Настройте отображение: выбрать <code>file.link</code> и <code>lesson_number</code>/<code>title</code> в карточке

4️⃣ <b>Планирование (два варианта):</b>
   - <b>Ручной (Make.md UI):</b> Перетащите заметку в дату на календаре — Make.md обновит frontmatter (если включено <code>Sync Context Fields to Frontmatter</code>).
   - <b>Полуавтоматический (QuickAdd):</b> Используйте QuickAdd → <code>Capture</code> или <code>New Lesson</code> для создания/редактирования урока, затем добавьте <code>planned_date</code> вручную или через QuickAdd.

5️⃣ <b>Быстрая команда:</b> Я могу добавить QuickAdd macro, который задаёт <code>planned_date</code> для выбранной заметки (выбираете дату в формате YYYY-MM-DD в QuickAdd input) и вписывает её в frontmatter — скажите, если нужно.

---

> [!tip] <b>Автоматизация:</b> Включите <code>saveAllContextToFrontmatter</code> в Make.md Settings — любые контекстные поля будут синхронизироваться в frontmatter автоматически при редактировании в Make.md интерфейсе.

---

## ⚡ Что могу сделать для вас

- ➕ Добавить QuickAdd macro <b>Set planned_date</b> (ввод даты → записать в frontmatter для текущего файла)
- 🤖 Автоматически проставить <code>planned_date</code> для всех уроков последовательно, начиная с <code>2026-04-16</code> (вам подтвердить)

<div style="margin-top: 18px;">
  <b>Что предпочитаете?</b> QuickAdd макрос для ручной установки дат в UI Make.md, или автоматическое проставление дат во все уроки по порядку начиная с <code>2026-04-16</code>?
</div>

---

## 🧭 Hub Connection
- [[02_LEARNING/Index|Domain Hub]]


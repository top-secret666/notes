
<div align="center">
  <img src="https://images.unsplash.com/photo-1464983953574-0892a716854b?auto=format&fit=crop&w=600&q=80" alt="Words To Learn" width="340" style="border-radius: 16px; margin-bottom: 12px;" />
  <h1>🗂️ Слова на выучить</h1>
</div>

---

Краткая панель для управления захваченными словами (теги <code>#unknown</code> / <code>#vocab</code>).

> [!tip] <b>Инструкция:</b> создавайте слова через QuickAdd → <code>Capture unknown word</code> (шаблон <code>Unknown-Word-Template.md</code>). После создания заполняйте <b>translation:</b> и <b>context:</b>; поле <b>due</b> определяет следующую дату повтора.

---

## 📅 Сегодня — urgente
```dataview
LIST FROM "Interview-Prep/english"
WHERE contains(tags, "unknown") AND date(due) = date(now)
SORT file.name asc
```

---

## ⏰ Просроченные
```dataview
TABLE file.link AS Note, word, translation, due, review_interval
FROM "Interview-Prep/english"
WHERE contains(tags, "unknown") AND due AND date(due) < date(now)
SORT due asc
```

---

## 🗓️ Мини-календарь — следующие 14 дней (быстрый обзор)
```dataviewjs
const pages = dv.pages('"Interview-Prep/english"').where(p => p.due && p.tags && p.tags.includes('unknown'));
const start = dv.date('now');
for (let i = 0; i < 14; i++) {
  const day = start.plus({ days: i });
  const dayStr = day.toISODate();
  const items = pages.filter(p => { try { return dv.date(p.due) && dv.date(p.due).toISODate() === dayStr } catch(e){ return false } });
  if (items.length) {
    dv.header(4, day.toFormat('yyyy-LL-dd (ccc)'));
    dv.list(items.map(it => dv.fileLink(it.file.path)));
  }
}
```

---

## 📋 Все слова — таблица
```dataview
TABLE word, translation, context, due, review_interval, file.link AS Note
FROM "Interview-Prep/english"
WHERE contains(tags, "unknown")
SORT due asc
```

---

## ⚡ Быстрые команды
- Translate selection: назначьте хоткей для команды плагина перевода (Settings → Hotkeys).
- Capture unknown word: QuickAdd → <code>Capture unknown word</code> (можно назначить хоткей через Settings → Hotkeys → QuickAdd: run choice).

---

> [!info] Если хотите, могу автоматически добавить в шаблон поля для Spaced Repetition (например, <code>efactor</code>, <code>repetitions</code>) и настроить интеграцию с плагином Spaced Repetition или AnkiConnect — скажите, какой вариант предпочитаете.

---

## 🧭 Hub Connection
- [[02_LEARNING/Index|Domain Hub]]


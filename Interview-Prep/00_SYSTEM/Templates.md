

<div style="width:100%; max-width:700px; margin:0 auto 18px auto; border-radius: 18px; background: linear-gradient(90deg, #6366f1 0%, #06b6d4 100%); color: #fff; padding: 28px 18px 18px 18px; box-shadow: 0 2px 12px #0001; text-align:center;">
  <span style="font-size:2.5em;">📋</span>
  <h1 style="margin: 0 0 8px 0; font-size:2em; font-weight:800; letter-spacing:1px; color:#fff;">00 — Шаблоны заметок</h1>
</div>

---

## 🗓️ Daily note template

<div style="background: #f7fafc; border-radius: 12px; padding: 18px; margin-bottom: 18px;">
<b>Дата:</b> <code>{{date}}</code>  
#interview #daily
</div>

### 🔗 Quick links

- [[Focus-Today]]
- [[Interview-Prep/Today-Panel]]
- [[06_SECOND_BRAIN/weekly-notes/weekly-kanban]]
- [[02_LEARNING/English/english-learning/English-Task-Template]]

---

### 📌 Next requirement (auto)
```dataviewjs
const path = "Interview-Prep/Company-Requirements.md";
const content = await dv.io.load(path);
const lines = content.split(/\r?\n/).map(l => l.trim());
const items = lines.filter(l => /^- \[\s?\]\s*/.test(l)).map(l => l.replace(/^- \[\s?\]\s*/, '')).filter(Boolean);
if (items.length) {
  dv.paragraph("Today focus: " + items[0]);
} else {
  dv.paragraph("Today focus: maintenance / mock interview");
}
```

---

### 📚 Next lesson reminder (auto)
```dataviewjs
// Find next lesson robustly: consider tags, frontmatter, and filename patterns
const allPages = dv.pages('"Interview-Prep"').values;
const candidates = Array.from(allPages).filter(p => {
  const tags = p.tags ?? p.file?.tags ?? [];
  const hasLessonTag = Array.isArray(tags) ? tags.includes('lesson') : String(tags).includes('lesson');
  const hasNumber = typeof p.lesson_number !== 'undefined';
  const nameLooksLike = (p.file && p.file.name && String(p.file.name).toLowerCase().includes('lesson'));
  return (hasLessonTag || hasNumber || nameLooksLike) && ((p.status ?? 'in-progress') !== 'done');
});
candidates.sort((a,b) => {
  const na = a.lesson_number ?? 999;
  const nb = b.lesson_number ?? 999;
  if (na !== nb) return na - nb;
  const fa = a.file?.name ?? '';
  const fb = b.file?.name ?? '';
  return fa.localeCompare(fb);
});
if (candidates.length) {
  const next = candidates[0];
  dv.paragraph("Next lesson: " + dv.fileLink(next.file.path));
} else {
  dv.paragraph("All lessons done — time for mock interviews!");
}
```

---

<div align="center">
  <img src="https://images.unsplash.com/photo-1465101178521-c1a9136a3b99?auto=format&fit=crop&w=600&q=80" alt="Notes Inspiration" width="320" style="border-radius: 16px; margin-top: 18px;" />
  <br>
  <sub>Используй шаблоны для ускорения и красоты своих заметок!</sub>
</div>

### Weekly checklist reminder (if Monday)
```dataviewjs
const today = new Date();
if (today.getDay() === 1) { // Monday
  dv.paragraph("Weekly checklist: [[Interview-Prep/Weekly-Checklist]]");
}
```

Daily auto-test (5-10 min)
- [ ] English: 1 sentence in Present Simple #english #today #test
- [ ] English: 1 sentence in Present Continuous #english #today #test
- [ ] Java: 1 OOP definition #java #today #test
- [ ] Java: 1 collection + use case #java #today #test
- [ ] Reflection: 1 mistake + fix #today #test
score:: __ / 5

Mini speaking survey (2-3 min)
- [ ] Spoke 60-90 sec without stopping #english #speaking #test
- [ ] Used 3 flashcard phrases #english #speaking #test
- [ ] Clear pronunciation (self-check) #english #speaking #test
- [ ] Confidence: 1-5 ___ #english #speaking

- Техника (цель):
  - [ ] Короткая задача (код/теория) — 30–90 мин #java #today
- Английский (цель):
  - [ ] Gram/ Vocab / Speaking — 20–45 мин #english #today
- Проект (чеклист):
  - [ ] small commit/README update #projects #today
  - [ ] push + заметка в Obsidian (ссылка) #projects
- Самочувствие / энергия: (0–10)
- Комментарии / затруднения:

# Project checklist template

Проект: {{project-name}}
Репозиторий: {{repo-link}}

Основная цель: (четко — что нужно довести)

Quick wins (сделать в первую очередь):
- [ ] README: краткое описание + quickstart
- [ ] .env.example
- [ ] Docker compose / run script
- [ ] Минимальное тестовое покрытие / smoke test
- [ ] Demo: gif или короткое видео

Stretch goals:
- [ ] Доп. тесты
- [ ] CI workflow (lint/tests)
- [ ] Метрики/logging docs

Как отмечать прогресс в Obsidian
- Создай daily note и добавь ссылку на коммит и короткий комментарий: что сделал, сколько времени потратил, что осталось.

---

# Примечания по форматированию
- Используй H1/H2 для заголовков, короткие списки и чеклисты.
- Скриншоты/гифы добавляй в папку `Interview-Prep/media` и вставляй ссылкой.
- Метки: поставь `#interview`, `#java`, `#english` в верхней части заметки для удобной фильтрации.








dv.paragraph(`Lessons: ${completed}/${total} (${percent}%)`);
dv.paragraph(`Requirements: ${done}/${total} (${percent}%)`);
dv.paragraph(`Tests completed this week: ${tests}`);


<div align="center">
  <img src="https://images.unsplash.com/photo-1515378791036-0648a3ef77b2?auto=format&fit=crop&w=600&q=80" alt="Progress Dashboard" width="340" style="border-radius: 16px; margin-bottom: 12px;" />
  <h1>📈 <span style="color:#3b82f6;">Comprehensive Progress Dashboard</span></h1>
</div>

---

#progress #dashboard

---


## ✅ Lesson Completion (auto)
<div style="background: #f0f8ff; border-radius: 10px; padding: 10px 18px;">
```dataviewjs
const lessons = dv.pages('"Interview-Prep"')
  .where(p => p.file.tags && p.file.tags.includes('lesson'))
  .sort(p => p.lesson_number ?? 999, 'asc');
const completed = lessons.filter(l => l.status === 'done').length;
const total = lessons.length;
const percent = total ? Math.round((completed / total) * 100) : 0;
dv.paragraph(`Lessons: ${completed}/${total} (${percent}%)`);
```
</div>

---


## 📋 Requirements Coverage (auto)
<div style="background: #fffbe6; border-radius: 10px; padding: 10px 18px;">
```dataviewjs
const reqPath = "Interview-Prep/Company-Requirements.md";
const content = await dv.io.load(reqPath);
const done = (content.match(/- \[x\]/gi) || []).length;
const todo = (content.match(/- \[ \]/g) || []).length;
const total = done + todo;
const percent = total ? Math.round((done / total) * 100) : 0;
dv.paragraph(`Requirements: ${done}/${total} (${percent}%)`);
```
</div>

---


## 🧪 Weekly Test Progress (last 7 days)
<div style="background: #f6ffed; border-radius: 10px; padding: 10px 18px;">
```dataviewjs
const tests = dv.pages('"Interview-Prep"')
  .where(p => p.file.tags && p.file.tags.includes('test'))
  .where(p => p.file.ctime >= dv.date('now').minus({days: 7}))
  .length;
dv.paragraph(`Tests completed this week: ${tests}`);
```
</div>

---


## 🛠️ Project Status (auto)
<div style="background: #e6f7ff; border-radius: 10px; padding: 10px 18px;">
```dataview
TABLE status, progress
FROM "Interview-Prep"
WHERE contains(file.tags, "project")
SORT file.name asc
```
</div>

---


## 🚀 Next Actions
<div style="background: #fffbe6; border-radius: 10px; padding: 10px 18px;">
- [ ] Complete next lesson: [[02_LEARNING/Java_Backend/java-lessons/Lessons-Index]]
- [ ] Mark requirements as done after lessons
- [ ] Run weekly mock interview
- [ ] Update project logs
</div>

---


## 🔗 Quick Links
<div style="background: #f0f8ff; border-radius: 10px; padding: 10px 18px;">
- [[Interview-Prep/Start-UI]]
- [[Focus-Today]]
- [[06_SECOND_BRAIN/weekly-notes/weekly-kanban]]
- [[Interview-Prep/Company-Requirements]]
</div>


<div align="center">
  <img src="https://images.unsplash.com/photo-1465101178521-c1a9136a3b99?auto=format&fit=crop&w=600&q=80" alt="Progress Inspiration" width="320" style="border-radius: 16px; margin-top: 18px;" />
  <br>
  <sub style="color:#3b82f6; font-size:1.1em;">Двигайся вперёд и отмечай каждый шаг!</sub>
</div>








<div align="center">
  <img src="https://images.unsplash.com/photo-1464983953574-0892a716854b?auto=format&fit=crop&w=600&q=80" alt="Lessons Index" width="340" style="border-radius: 16px; margin-bottom: 12px;" />
  <h1>📚 Lessons Index</h1>
</div>

---

#lesson #index

---

## ⏭️ Next lesson (auto)
```dataviewjs
const lessons = dv.pages('"Interview-Prep"')
  .where(p => p.file.tags && p.file.tags.includes('lesson'))
  .where(p => (p.status ?? 'in-progress') != 'done')
  .sort(p => p.lesson_number ?? 999, 'asc');
const next = lessons.first();
if (next) {
  dv.paragraph(dv.fileLink(next.file.path));
}
```

---

## 📋 All lessons
```dataview
TABLE lesson_number, lesson_version, status
FROM "Interview-Prep"
WHERE contains(file.tags, "lesson")
SORT lesson_number asc
```

---

## ➕ Add new lesson
- Create a new note and add tags: <b>#lesson</b>
- Add frontmatter: <b>lesson_number, lesson_version, status</b>

<div align="center">
  <img src="https://images.unsplash.com/photo-1515378791036-0648a3ef77b2?auto=format&fit=crop&w=600&q=80" alt="Lessons Inspiration" width="320" style="border-radius: 16px; margin-top: 18px;" />
  <br>
  <sub>Учись последовательно — и ты увидишь результат!</sub>
</div>







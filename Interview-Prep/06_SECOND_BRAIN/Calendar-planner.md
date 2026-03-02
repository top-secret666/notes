startDate: 2026-04-16
weeks: 8
sticker: lucide//calendar


<div style="width:100%; max-width:700px; margin:0 auto 18px auto; border-radius: 18px; background: linear-gradient(90deg, #6366f1 0%, #06b6d4 100%); color: #fff; padding: 28px 18px 18px 18px; box-shadow: 0 2px 12px #0001; text-align:center;">
  <span style="font-size:2.5em;">🗓️</span>
  <h1 style="margin: 0 0 8px 0; font-size:2em; font-weight:800; letter-spacing:1px; color:#fff;">Calendar Planner — Lessons & Schedule</h1>
</div>

---

<b>Start date (from frontmatter):</b> <code>startDate</code> — calendar will show weeks starting on Monday and list lessons assigned to workdays sequentially.

> [!info] <b>Edit <code>startDate</code> in frontmatter to change the planning start.</b>

---

```dataviewjs
// Read config
const cfg = dv.current().file ? dv.current() : {};
const start = dv.date(cfg.startDate ?? '2026-04-16');
const weeks = cfg.weeks ?? 8;

// Collect lessons sorted by lesson_number
const lessons = dv.pages('"Interview-Prep/lessons"')
  .where(p => p.lesson_number)
  .sort(p => p.lesson_number, 'asc')
  .values;

// Schedule lessons on next working days (Mon-Fri)
let scheduled = [];
let d = start;
for (let l of lessons) {
  // find next Mon-Fri
  while ([6,0].includes(d.toJSDate().getDay())) {
    d = d.plus({ days: 1 });
  }
  scheduled.push({ date: d, lesson: l });
  d = d.plus({ days: 1 });
}

// Render week grid starting on Monday of start
let startOfWeek = start;
while (startOfWeek.toJSDate().getDay() !== 1) startOfWeek = startOfWeek.minus({ days: 1 });

for (let w = 0; w < weeks; w++) {
  const weekStart = startOfWeek.plus({ days: w * 7 });
  dv.header(3, weekStart.toFormat('yyyy-LL-dd') + ' — Week ' + (w+1));
  // table header
  let rows = [];
  for (let day = 0; day < 7; day++) {
    const dayDate = weekStart.plus({ days: day });
    const items = scheduled.filter(s => dv.date(s.date).toISODate() === dayDate.toISODate());
    rows.push({ day: dayDate.toFormat('ccc dd'), items });
  }
  // Print simple table
  dv.table(['Day', 'Lessons / Items'], rows.map(r => [r.day, r.items.length ? r.items.map(i => `${i.lesson.lesson_number}: ${i.lesson.file.name} ${dv.fileLink(i.lesson.file.path)}`) : '']));
}

// Also list planned schedule
dv.header(2, 'Planned schedule (all)');
if (scheduled.length) dv.table(['Date','Lesson','Link'], scheduled.map(s=>[s.date.toISODate(), s.lesson.lesson_number, dv.fileLink(s.lesson.file.path)]));
else dv.paragraph('No lessons found to schedule.');
```









<div style="width:100%; max-width:700px; margin:0 auto 18px auto; border-radius: 18px; background: linear-gradient(90deg, #6366f1 0%, #06b6d4 100%); color: #fff; padding: 28px 18px 18px 18px; box-shadow: 0 2px 12px #0001; text-align:center;">
  <span style="font-size:2.5em;">📊</span>
  <h1 style="margin: 0 0 8px 0; font-size:2em; font-weight:800; letter-spacing:1px; color:#fff;">Projects Dashboard</h1>
</div>

---

#projects #dashboard

---

## 📋 Status table
```dataview
TABLE status, progress, repo
FROM "Interview-Prep"
WHERE project
SORT project asc
```

---

## 🚦 Progress (auto)
```dataviewjs
const pages = dv.pages('"Interview-Prep"').where(p => p.project);
const rows = pages.map(p => {
  const pct = p.progress ?? 0;
  const bar = '█'.repeat(Math.round(pct/10)) + '░'.repeat(10 - Math.round(pct/10));
  return [p.project, p.status ?? '', `${pct}%`, bar];
});

dv.table(['Project', 'Status', 'Progress', 'Bar'], rows);
```

---

## 🔗 Quick links
- [[Project-RGR]]
- [[Project-Witcher]]
- [[Project-Christmas]]







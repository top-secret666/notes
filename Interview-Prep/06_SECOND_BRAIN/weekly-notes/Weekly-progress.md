
<div align="center">
  <img src="https://images.unsplash.com/photo-1519125323398-675f0ddb6308?auto=format&fit=crop&w=600&q=80" alt="Weekly Progress" width="340" style="border-radius: 16px; margin-bottom: 12px;" />
  <h1>📈 Weekly Progress</h1>
</div>

---

#progress #weekly

---

## 📊 Table (auto)
```dataviewjs
const pages = dv.pages('"Interview-Prep"')
  .where(p => p.week)
  .sort(p => p.week, 'asc');

const rows = pages.map(p => {
  const total = p.total_score ?? 0;
  const bar = '█'.repeat(Math.min(10, Math.round(total / 2))) + '░'.repeat(Math.max(0, 10 - Math.round(total / 2)));
  return [p.week, p.english_score ?? '', p.java_score ?? '', p.projects_score ?? '', total, bar];
});

dv.table(['Week', 'English', 'Java', 'Projects', 'Total', 'Bar'], rows);

const totals = pages.map(p => p.total_score ?? 0);
const avg = totals.length ? Math.round(totals.reduce((a,b)=>a+b,0) / totals.length) : 0;
const avgBar = '█'.repeat(Math.min(10, Math.round(avg / 2))) + '░'.repeat(Math.max(0, 10 - Math.round(avg / 2)));

dv.paragraph(`Average total: ${avg}/20  ${avgBar}`);
```

---

## ✅ Manual check
- [ ] Weekly review done
- [ ] 1 mini-test done
- [ ] 1 project update done







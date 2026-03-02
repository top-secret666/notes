---
sticker: lucide//clock-10
---


<div style="width:100%; max-width:700px; margin:0 auto 18px auto; border-radius: 18px; background: linear-gradient(90deg, #6366f1 0%, #06b6d4 100%); color: #fff; padding: 28px 18px 18px 18px; box-shadow: 0 2px 12px #0001; text-align:center;">
  <span style="font-size:2.5em;">⏳</span>
  <h1 style="margin: 0 0 8px 0; font-size:2em; font-weight:800; letter-spacing:1px; color:#fff;">Auto Progress (7 days)</h1>
</div>

---

#progress #auto

---

```dataviewjs
const since = dv.date("today").minus({ days: 7 });
const pages = dv.pages('"Interview-Prep"').where(p => p.file.mtime >= since);
let done = 0;
let total = 0;

for (const p of pages) {
  const content = await dv.io.load(p.file.path);
  const lines = content.split("\n").filter(l => l.includes("#test"));
  total += lines.filter(l => l.match(/- \[ \]/)).length;
  done += lines.filter(l => l.match(/- \[x\]/i)).length;
}

const percent = total ? Math.round((done / total) * 100) : 0;
const bar = "█".repeat(Math.round(percent / 10)) + "░".repeat(10 - Math.round(percent / 10));

dv.paragraph(`<b>Tests done:</b> ${done}/${total} <b>(${percent}%)</b> <span style='font-size:1.2em;'>${bar}</span>`);
```

---

## 📋 What counts
- Любая задача с тегом <b>#test</b> в daily notes.
- Отмечай чекбоксы, и прогресс считается автоматически.







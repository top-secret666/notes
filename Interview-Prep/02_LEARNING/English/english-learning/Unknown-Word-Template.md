word: <% tp.file.selection() %>
translation:
context: <% tp.file.cursor() %>
date_added: <% tp.date.now("YYYY-MM-DD") %>
due: <% tp.date.now("YYYY-MM-DD", 1) %> # default next day
review_interval: 1
tags: [english, vocab, unknown]

<div align="center">
	<img src="https://images.unsplash.com/photo-1465101046530-73398c7f28ca?auto=format&fit=crop&w=600&q=80" alt="Unknown Word" width="340" style="border-radius: 16px; margin-bottom: 12px;" />
	<h1>🆕 Unknown Word — <% tp.file.selection() %></h1>
</div>

---

**Word:** <% tp.file.selection() %>

**Translation:** 

**Context / sentence:**

**Notes:**

**Next review:** <% tp.date.now("YYYY-MM-DD", 1) %>

---

> [!tip] <b>Use your Translate/DeepL plugin to translate the selected word before saving, or fill <code>translation:</code> after capture.</b>

---

## 🧭 Hub Connection
- [[02_LEARNING/Index|Domain Hub]]


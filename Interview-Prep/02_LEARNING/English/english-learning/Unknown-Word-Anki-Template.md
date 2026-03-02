anki-deck: Interview::Vocab
anki-model: Basic
word: <% tp.file.selection() %>
translation:
context: <% tp.file.cursor() %>
date_added: <% tp.date.now("YYYY-MM-DD") %>
tags: [english, vocab, unknown, anki]

<div align="center">
	<img src="https://images.unsplash.com/photo-1515378791036-0648a3ef77b2?auto=format&fit=crop&w=600&q=80" alt="Anki Card" width="340" style="border-radius: 16px; margin-bottom: 12px;" />
	<h1>🃏 Anki Card — <% tp.file.selection() %></h1>
</div>

---

## 📝 Front
<% tp.file.selection() %>

---

## 💡 Back
- <b>Translation:</b> 
- <b>Context:</b>
- <b>Notes:</b>

---

> [!tip] <b>Usage:</b>
> - Create via QuickAdd → <code>Capture unknown + Anki</code> (it will open the new note).
> - Fill <code>translation:</code> and adjust <b>Front</b>/<b>Back</b> if needed.
> - To push to Anki: use your Anki plugin (AnkiConnect / anki-sync-plus) or run the helper script <code>tools/send_to_anki.py</code> (I can add that for you).

---

## 🧭 Hub Connection
- [[02_LEARNING/Index|Domain Hub]]


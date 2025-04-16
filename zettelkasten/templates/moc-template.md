---
note-type: moc
file-path: <%= tp.file.path() %>
created: <% tp.date.now("YYYY-MM-DD") %>
status: curated
tags: [moc]
---

# 🗺️ MOC: <% tp.file.title %>

> Este é um mapa de conteúdo que organiza tópicos relacionados sobre **<% tp.file.title %>**.

## 📁 Subtópicos
- [[subtópico 1]]
- [[subtópico 2]]

## 🔗 Notas Relacionadas
<% tp.system.list_all_files().filter(f => f.includes(tp.file.title.toLowerCase())).forEach(file => { %>
- [[<%= file.replace(".md", "") %>]]
<% }) %>

## 📚 Leituras Recomendadas
- [[literature-notes/exemplo]]

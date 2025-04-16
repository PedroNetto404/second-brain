````markdown
# 🧠 Zettelkasten Notes Repository

Este repositório implementa o método **Zettelkasten** para organização, desenvolvimento e retenção de conhecimento ao longo do tempo. Inspirado no sistema criado por Niklas Luhmann, este repositório digital replica a ideia de um "arquivo vivo", onde cada nota é uma peça conectada de um grande quebra-cabeça intelectual.

![Zettelkasten Visual Overview](./attachs/Zettelkasten_paper_schematic.webp)

---

## 📚 Sobre o Método Zettelkasten

**Zettelkasten**, do alemão "caixa de notas", é uma técnica de escrita e organização de conhecimento que transforma a maneira como registramos, conectamos e desenvolvemos ideias. Seu criador, o sociólogo Niklas Luhmann, escreveu mais de 70 livros e 400 artigos usando esse sistema. A chave do sucesso do Zettelkasten está na **interconexão entre notas atômicas**, o que facilita a geração de insights e a escrita fluida.

---

## 🧩 Estrutura do Repositório

```bash
.
├── 📁 [attachs](./attachs)               # Imagens de apoio e diagramas
├── 📁 [fleeting_notes](./fleeting_notes) # Notas rápidas ou temporárias
├── 📁 [literature_notes](./literature_notes) # Notas derivadas de leituras
├── 📁 [permanent_notes](./permanent_notes)   # Notas permanentes e interconectadas
````

---

## 🔧 Workflow do Zettelkasten

A seguir, o processo sugerido para utilizar este repositório:

### 1. 📝 Fleeting Notes

Anotações rápidas e efêmeras feitas durante estudos, reuniões ou reflexões. São armazenadas em [`/fleeting_notes`](https://chatgpt.com/g/g-NgAcklHd8-scispace/c/fleeting_notes) e servem como matéria-prima para as próximas etapas. Status: `raw`.

### 2. 📖 Literature Notes

Após a leitura de livros, artigos ou vídeos, sintetize o conteúdo em suas palavras e registre aqui. Essas notas são organizadas por fonte e guardadas em [`/literature_notes`](https://chatgpt.com/g/g-NgAcklHd8-scispace/c/literature_notes). Status: `processed`.

### 3. 💡 Permanent Notes

Notas com uma única ideia clara, escritas com linguagem própria e conectadas a outras. Vivem em [`/permanent_notes`](https://chatgpt.com/g/g-NgAcklHd8-scispace/c/permanent_notes). Status: `permanent`.

### 4. 🗺️ MOC (Map of Content)

Notas de organização que reúnem links para notas relacionadas e criam visões estruturadas de um tópico. Status: `curated`.

---

## 🧾 Metadados YAML por Tipo de Nota

|Campo|Tipo|Descrição|
|---|---|---|
|`note-type`|`string`|Tipo da nota (`fleeting_note`, `literature_note`, `permanent_note`, `moc`)|
|`file-path`|`string`|Caminho completo do arquivo|
|`created`|`date`|Data de criação da nota|
|`status`|`string`|Progresso da nota (`raw`, `processed`, `permanent`, `curated`)|
|`title`|`string`|Título da nota permanente (opcional)|
|`source`|`string`|Origem da leitura (aplicável a literature_note)|
|`tags`|`list[string]`|Palavras-chave úteis para filtragem com plugins|

---

## 📸 Exemplos Visuais

### Zettelkasten no Notion

![Notas no Notion com Zettelkasten](https://chatgpt.com/g/g-NgAcklHd8-scispace/c/attachs/notas-zettelkasten-notion.jpg)

### Organização visual de ideias

![Diagrama de notas](https://chatgpt.com/g/g-NgAcklHd8-scispace/c/attachs/maxresdefault.jpg)

---

## 🚀 Comece Agora

1. Capture ideias em `/fleeting_notes`
    
2. Reflita e transcreva para `/literature_notes`
    
3. Modele suas ideias finais em `/permanent_notes`
    
4. Organize o todo com mapas de conteúdo em `/moc`
    

---

## 🧭 Referências

- [Zettelkasten overview — Wikipedia](https://en.wikipedia.org/wiki/Zettelkasten)
    
- [Método explicado (YouTube)](https://www.youtube.com/watch?v=lo4v4t06uD0)
    

---

> “A escrita é pensamento externado – e o Zettelkasten é o espelho dessa mente em rede.”
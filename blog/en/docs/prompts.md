# Prompts

The Prompts Tab (accessible via toolbar menu or Configuration) lets you customize how the plugin communicates with AI.

## Persona

Define your research background and goals. This text is prepended to every prompt sent to AI.

### Example Personas

- "As a literature professor, I focus on narrative techniques and literary analysis."
- "I'm researching 19th century European history, especially political movements."
- "As a student, I want simple explanations suitable for beginners."

The more specific your persona, the more relevant AI responses will be.

### Tips

- Include your field of study or profession
- Mention your expertise level (beginner, expert, etc.)
- Describe what aspects you care about most

## Prompt Templates

Three customizable templates:

### 1. Single Book Prompt

Used when asking about one book.

**Available variables:** `{title}`, `{author}`, `{publisher}`, `{pubyear}`, `{language}`, `{series}`, `{query}`

### 2. Multi-Book Prompt

Used when asking about multiple selected books.

**Available variables:** `{books_metadata}`, `{query}`

### 3. Random Question Prompt

Used when generating random questions.

**Available variables:** `{title}`, `{author}`, `{language}`

## Use Interface Language

When enabled, the plugin adds an instruction asking AI to respond in your current plugin language. Useful if you want responses in a specific language regardless of the book's language.

## Reset to Default

Click "Reset Prompts to Default" to restore all prompts and settings to their original values.

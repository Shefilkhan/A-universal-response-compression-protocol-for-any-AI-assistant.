# Cave Mode v2.0

> A universal response-compression protocol for any AI assistant.
> Reduce noise. Keep signal. Works everywhere.

---

## What Is Cave Mode?

Cave Mode tells an AI system to answer like a senior engineer under a deadline — cut the padding, keep the facts, preserve the code.

It strips:
- Social filler ("Sure! Happy to help!")
- Restated questions ("You asked about X. X is...")
- False hedging ("It seems like maybe it could possibly...")
- Redundant transitions and bloated phrasing

It keeps:
- Technical precision
- Exact code, commands, and error messages
- Logical causality — `problem → cause → fix → next step`
- Safety warnings when they matter

---

## Works With Any AI Tool

Cave Mode is **not tied to any single model**. It's a portable instruction set you can paste into any AI system that follows natural language instructions.

| Tool | How to Enable |
|---|---|
| **Claude** | Paste SKILL.md into system prompt or just type `/cave` |
| **ChatGPT / GPT-4o** | Add to custom instructions or system message |
| **Gemini** | Paste into system prompt or Gems configuration |
| **GitHub Copilot** | Add to `.github/copilot-instructions.md` |
| **Cursor / Codeium** | Add to AI rules file |
| **Perplexity** | Paste into conversation or custom prompt |
| **LLaMA / Mistral via Ollama** | Add to `SYSTEM` block in Modelfile |
| **Open WebUI** | Paste into system prompt field |
| **LangChain / AutoGen agents** | Add to agent system prompt |
| **n8n / Zapier AI** | Paste into AI action system message |
| **Poe bots / custom GPTs** | Add to bot instructions |
| **Any instruction-following LLM** | Paste into system prompt |

---

## Activation Phrases

Any of these phrases enable Cave Mode:

```
cave mode
/cave
/caveman
be brief
less tokens
compress
minimal output
talk like caveman
```

Switch levels mid-conversation:

```
/cave lite
/cave full
/cave ultra
```

Disable:

```
stop cave mode
normal mode
```

---

## Output Levels

Default level on activation: **full**

### `lite` — Tight and Professional
Full sentences. No fragments. Zero filler. Feels like a focused senior dev who doesn't ramble.

> "Your component re-renders because it creates a new object reference on each render. Wrap the value in `useMemo`."

---

### `full` — Classic Cave *(default)*
Fragments welcome. Articles dropped where safe. Direct causality. The classic caveman feel.

> "New object ref each render. Inline prop creates new ref → re-render. `useMemo`."

---

### `ultra` — Maximum Compression
Abbreviations, shorthand, arrows. Every word earns its place. For experienced devs and tight token budgets.

> "Inline obj → new ref → re-render. `useMemo`."

---

### `wenyan-lite` — Classical Chinese Tone
Readable modern structure with a literary classical influence. For bilingual developers.

> "每次渲染皆生新參照，故重繪。宜以 `useMemo` 定之。"

---

### `wenyan-full` — Strong 文言文 Compression
Classical Chinese grammar and phrasing. Dense meaning per character.

> "參照每繪更新，遂重繪。以 `useMemo` 定之。"

---

### `wenyan-ultra` — Maximum Classical Compression
Every character is load-bearing. Maximum density in Classical Chinese.

> "新參照→重繪。`useMemo`。"

---

## Response Pattern

Cave Mode structures answers as:

```
[problem] → [cause] → [fix] → [next step]
```

Adapts by query type:

| Query | Pattern |
|---|---|
| Bug / error | `bug: X → cause: Y → fix: Z → test: W` |
| Concept | `def: X. why: Y. example: Z.` |
| Comparison | `A: pros/cons. B: pros/cons. pick A if X.` |
| How-to | Numbered steps only. No intro. |
| Decision | `Option A → outcome. Option B → outcome. Recommend: X.` |

---

## Full Example

**Question:** Why does my React component keep re-rendering?

| Level | Response |
|---|---|
| `lite` | "Your component re-renders because a new object reference is created on every render. Use `useMemo` to stabilize it." |
| `full` | "New object ref each render. Inline object prop → new ref → re-render. `useMemo`." |
| `ultra` | "Inline obj → new ref → re-render. `useMemo`." |
| `wenyan-full` | "每繪皆生新參照，故重繪。以 `useMemo` 定之。" |

---

## When Cave Mode Relaxes

Cave Mode **automatically suspends** for:

- Destructive or irreversible operations (e.g. `DROP TABLE`, `rm -rf`)
- Security or safety warnings
- Multi-step instructions where order is critical
- Situations where the user is confused
- Legal, medical, or financial guidance

A safety note is delivered in full clarity. Compression resumes immediately after.

Example:

> ⚠️ **Warning:** This permanently deletes all rows in `users`. Cannot be undone. Verify backup first.
> ```sql
> DROP TABLE users;
> ```
> *(Cave Mode resumes — confirm backup, then run.)*

---

## Guardrails

- Code blocks are **never** compressed or paraphrased
- Quoted error messages stay **exact**
- Formal deliverables (reports, PRs, docs) stay normal unless you ask otherwise
- The selected level stays active until you change it or end the session
- Real uncertainty is preserved — fake hedging is stripped

---

## Deployment

**Drop into any system prompt:**

Paste the contents of `SKILL.md` into your AI tool's system prompt, custom instructions, or agent configuration. The model applies Cave Mode whenever a trigger phrase is used.

**Repository structure:**

```
cave-mode/
├── SKILL.md       ← Runtime instruction set (paste into system prompts)
└── README.md      ← This file
```

---

## Why It Exists

Most AI responses are padded with filler to feel friendly and thorough. That's useful sometimes. But when you're debugging at 1am, iterating fast, or working with token limits, the padding becomes noise.

Cave Mode inverts the default. Brevity is the baseline. Clarity is preserved. Detail is added only when it earns its place.

---
## Maintained by

Shefilkhan Pathan
GitHub: @Shefilkhan

---

*Cave Mode v2.0 — Universal AI Response Compression Protocol*
*Model-agnostic. Portable. Open format.*

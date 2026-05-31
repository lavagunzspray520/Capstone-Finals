---
inclusion: always
---

# Project Rule: Keep Context Files Updated

For this repository (AlertoMarikeño capstone), always keep the two context/memory
files in sync as work progresses:

- **`agent.md`** — project context and memory. Update the **Session Log** at the
  end of each working session, and add to the **Decision Log** whenever a notable
  decision is made. Keep the project overview, tech stack, and repo structure
  current as the project evolves.
- **`skills.md`** — skills matrix, task playbooks, glossary, and the
  **Chat-History Quick Reference** memory log. Append new playbooks and Q&A
  entries as they come up in conversation.

## When to update
- After any meaningful change to the repo (new code, new docs, new assets).
- After any decision about tech, scope, or approach.
- At the end of each chat/working session, summarize what was discussed and
  changed, and note what is next.

## How to update
- Keep entries factual and concise (what was discussed, what changed, what's next).
- Newest entries first in the Chat-History Quick Reference; chronological in the
  Session Log.
- Do not commit secrets (DB credentials, SMS/email API keys) into either file.

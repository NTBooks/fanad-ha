# Fanad — Home Assistant add-on repository

This repository lets you install **[Fanad](https://github.com/NTBooks/Fanad)** as a Home
Assistant App (add-on): a local-first personal scratchpad for tasks, notes, lists, timers and
light journaling. Your data stays in SQLite on your box; a local LLM (LM Studio / Ollama) does
the parsing. No nagging, no cloud by default, no telemetry.

## Install

1. In Home Assistant go to **Settings → Add-ons → Add-on store** (on newer installs: **Settings → Apps**).
2. Open the **⋮** menu (top right) → **Repositories**.
3. Add this URL:

   ```
   https://github.com/NTBooks/fanad-ha
   ```

4. Find **Fanad** in the store, click it, and **Install**.
5. Start it, open the **Web UI**, and connect a model in **Settings** (see the add-on's Documentation tab).

Prefer plain Docker? The same image runs anywhere:
`docker run -p 8787:8787 -v fanad:/data ghcr.io/ntbooks/fanad-app:latest`

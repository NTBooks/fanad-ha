# Fanad — documentation

Fanad is a local-first scratchpad (tasks, notes, lists, timers, light journaling). It stores
everything in SQLite on your Home Assistant box and uses a **local** LLM you point it at for
parsing and ranking. The LLM never invents data and never acts on your house.

## First run

1. **Start** the add-on and open the **Web UI** (sidebar panel, or the "Open Web UI" button).
2. Go to **⚙ Settings** and connect a model:
   - **LM Studio / Ollama:** pick the provider and enter the base URL. Use the **LAN IP** of the
     machine running the model (e.g. `http://192.168.1.50:1234/v1`), **not** `localhost` — Fanad
     runs in a container and `localhost` points at the container, not your desktop.
   - No model yet? Set the provider to **mock** (in the add-on Configuration tab) to try the
     flow with a built-in stub, then wire a real model later.
3. Text a snippet in the web chat, watch it get filed, and ask **"what should I do?"**.

## Configuration options

Only bootstrap settings live in the add-on **Configuration** tab (where the LLM is, the cloud
gate, auth mode). Everything else — LLM API keys, Telegram/Slack tokens, Home Assistant
connection — is set in Fanad's own **Settings** UI and stored encrypted in the database.

- **allow_cloud_llm** — off by default. Local providers keep everything on your box; turn this
  on only if you have no hardware to run a local model (then add a key in Settings).
- **auth_mode** — `none` (open UI, fine on a trusted LAN behind ingress) or `simple`
  (username + password + mandatory 2FA). Set up credentials in Settings **before** switching.
- **auth_reset** — break-glass: turn on + restart to force web login off if you get locked out.

## Ringing the house (optional)

Fanad can make timer/reminder dings ring your HA speakers and pass `ha <command>` to your Assist
agent. Enable the Home Assistant module in Fanad (**Settings**, or `optin ha` in chat), then add
your HA URL + a long-lived access token in **Settings → Home Assistant**.

## Backups & data — read this

- Your data lives in `/data` inside the add-on. **Uninstalling the add-on deletes `/data`** —
  back up first.
- HA's native backups include the add-on's `/data` (this add-on sets `backup: hot`), so a normal
  HA backup captures your Fanad database **and** its encryption key together. Restore brings both
  back. A backup that excludes this add-on's data is not a Fanad backup.

## Direct access (optional)

Ingress is the default UI. If you enable the optional `8787/tcp` port (Configuration → Network),
you can also reach the same UI/API directly at `http://<your-ha-ip>:8787` — useful for testing,
phones, or the `fanad` CLI/TUI client.

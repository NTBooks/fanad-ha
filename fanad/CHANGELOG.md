# Changelog

## 0.5.3

- Local accounts for family without Telegram: add a household name whose whole surface is its
  no-login remote-control link, so someone with no Telegram can still tap your house buttons. A
  local's link can be minted never-expiring, since the link is the account.

## 0.5.2

- Speed-dial toggle slots: give a pad number a second (OFF) command and it becomes an on/off toggle
  that alternates the device, kept in sync across Telegram, the web pad, and the no-login link.
  Remote-page buttons now fill on press and briefly lock against an accidental double-tap.
- Task detail view: `/view N` reads a task's full details and lets you edit its steps without
  starting it, on every surface.

## 0.5.1

- Shareable no-login remote-control links: mint a `/r/<token>` link that exposes one guest's
  speed-dial pad as a web page, so someone can tap your house buttons without a Telegram account or
  login. Fail-closed (requires web login to mint and use), revocable, with 1 / 7 / 30-day expiry.

## 0.5.0

- Dashboard notebook picker: a read-only token can now request a specific notebook's data with
  `?notebook=<id|main>` on the read endpoints, so a Home Assistant dashboard can switch between your
  notebooks without changing the account's current one.
- Speed dial now shows in the web sidebar, and the connect line handed back with a token is a
  zero-checkout `npx` one-liner (Node 24+), so the CLI client runs from a fresh terminal.

## 0.4.0

- Self-service dashboard token: send `token` in chat to mint the read-only credential a Home
  Assistant dashboard needs to read your Fanad data, no owner-only web panel required. Settings
  also gains an "Expires" picker (30 / 90 / 365 days / Never) when creating a token.

## 0.3.0

- Speed dial: the owner can program another Telegram account's 0-9 pad, mapping each slot to a
  Home Assistant command. That person sends a bare digit (or taps a button) and it fires only
  that command. Good for housemates or kids who should reach only a few devices.
- Medication module (opt-in): a calm daily-adherence logger with reminders and a web view.
- Web UI polish, plus a first-run demo that teaches the "command pad, not a chatbot" model.

## 0.2.1

- Auto-pairing: Fanad now reaches Home Assistant through the Supervisor proxy, so ringing the
  house works with no long-lived token to paste. Enable the HA module and pick your outputs.

## 0.2.0

- First Home Assistant App release of Fanad.
- Ingress web UI + optional direct `8787/tcp` access.
- Prebuilt multi-arch image (aarch64, amd64) from `ghcr.io/ntbooks/fanad-app`.
- Bootstrap options: LLM provider + URL, cloud gate, auth mode, KEK, break-glass reset.

# Changelog

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

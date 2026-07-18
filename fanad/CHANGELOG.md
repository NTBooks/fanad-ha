# Changelog

## 0.2.1

- Auto-pairing: Fanad now reaches Home Assistant through the Supervisor proxy, so ringing the
  house works with no long-lived token to paste. Enable the HA module and pick your outputs.

## 0.2.0

- First Home Assistant App release of Fanad.
- Ingress web UI + optional direct `8787/tcp` access.
- Prebuilt multi-arch image (aarch64, amd64) from `ghcr.io/ntbooks/fanad-app`.
- Bootstrap options: LLM provider + URL, cloud gate, auth mode, KEK, break-glass reset.

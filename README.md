# tharavad

Community Linux server for TinkerHub Kerala.  
Inspired by [Hack Club Nest](https://nest.hackclub.com).

## Structure

```
tharavad/
├── index.html              — landing page (tharavad.xyz)
├── zia0/                   — iptables rules for proxmox host and mattermost config 
├── tinkerspace-vm/         — user shell VM config
├── secure-vm/              — Authentik, Headscale, Vaultwarden
├── vps/                    — Caddy, nftables, turnserver
└── cli/                    — tinker-cli (coming soon)
```

## Access

Sign up: https://auth.tharavad.xyz/if/flow/tinkerhub-enrollment/  
SSH in: `ssh -p 2222 username@tharavad.xyz`

## Services

| URL | Service |
|-----|---------|
| auth.tharavad.xyz | Authentik - identity & SSO |
| vault.tharavad.xyz | Vaultwarden - secrets |
| headscale.tharavad.xyz | Headscale - VPN |
| chat.tharavad.xyz | Mattermost - chat |
| ctf.tharavad.xyz | rCTF - ctf |

## Replace Before Deploying

This repo includes a few secret placeholders that must be replaced before deployment.

| File | Value to replace | Notes |
|------|------------------|-------|
| `zia0/mattermost-config.json` | `smtp_password_here` | SMTP credential placeholder. Load from env or secret storage instead of committing a real value. |
| `zia0/mattermost-config.json` | `turn_static_auth_secret_here` | Static auth secret placeholder. This should match the TURN server shared secret. |
| `vps/turnserver.conf` | `STATIC_AUTH_SECRET_HERE` | TURN server shared secret placeholder. Replace with a strong random secret and keep it aligned with related app config. |

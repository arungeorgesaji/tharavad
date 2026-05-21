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

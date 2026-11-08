# noelcaverly.com

Personal site. Live at https://www.noelcaverly.com.

GitHub Pages deploys straight from `main` (Settings → Pages → Deploy from a branch); there is no deploy workflow or build step. `mods/` is a template for future game-mod pages and is not linked from the homepage yet.

The ambient monitor lives in [NoelCav/Ambient-Monitor](https://github.com/NoelCav/Ambient-Monitor); its dashboard is served from that repo's GitHub Pages and shown at https://www.noelcaverly.com/monitor/ by a Cloudflare Worker (setup in that repo's `cloud/README.md`). `monitor/index.html` is a fallback redirect for when the Worker isn't set up.

## Cloudflare setup (manual)
- [x] DNS A records for noelcaverly.com → GitHub Pages IPs (proxied):
        185.199.108.153 / .109.153 / .110.153 / .111.153
- [x] DNS CNAME www → noelcav.github.io (proxied)
- [x] SSL/TLS mode: Full (strict)
- [x] Redirect rule "Redirect Apex to WWW" template: noelcaverly.com → https://www.noelcaverly.com
      (GitHub only issues a cert for www, so the apex returns 526 without it)

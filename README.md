# Hi, I'm Ozy-666 👋

**A hobby project — I run a public, no-logs DNS resolver and give it to anyone who wants it. Not a product, not a business.**

🛡️ **[DNSDOH.ART](https://dnsdoh.art/)** — my public, no-logs DNS resolver that blocks ads & trackers and keeps your browsing private
🌐 **[ozy-666.github.io](https://ozy-666.github.io/)** — my homepage

---

## What it is

**[DNSDOH.ART](https://dnsdoh.art/)** is a public, encrypted DNS resolver I run as a hobby. In plain words, it does the "phone book" lookup your device makes every time you open a website — but it does it **privately and cleanly**:

- 🚫 **Blocks ads & trackers** — in every app, not just your browser
- 🔒 **Keeps you private** — your internet provider can't see which sites you visit
- ⚡ **Often makes pages faster** — less junk to load
- 💸 **No cost, no app, no logs** — nothing about you is ever recorded

It works on phones, computers, and routers — usually just **one setting**, no technical knowledge needed.

**→ [Set it up on your device](https://dnsdoh.art/setup.html)**

---

## Under the hood (for the technically curious)

You don't need any of this to use the service. It runs on three upstream programs, each rebuilt for this server, and **every speed claim is backed by a real benchmark**, not a guess.

| Part | In plain words | Repo |
|------|---------------|------|
| **nginx** | The front door: encrypted DoH and DoH3, post-quantum key exchange, Encrypted Client Hello | [nginx-edge](https://github.com/Ozy-666/nginx-edge) |
| **dnsdist** | Answers plain DNS, DoT and DoQ, and applies the ad, tracker and malware blocklists | - |
| **Unbound** | Checks that answers are genuine (DNSSEC) and fetches them over DoT from Cloudflare and Quad9 | [unbound-edge](https://github.com/Ozy-666/unbound-edge) |

**A favourite optimization - [Unbound on BoringSSL](https://github.com/Ozy-666/unbound-edge#why-boringssl):** checking the security signatures that prove a website's address is genuine was eating nearly half the server's effort. I swapped in Google's BoringSSL to do that work - **+14% more handled, -27% worst-case waiting**, with a one-command undo kept ready.

**Retired in October 2026:** until then the service ran on my own forks of [AdGuard Home](https://github.com/Ozy-666/AdGuardHome-edge-spec), [dnsproxy](https://github.com/Ozy-666/dnsproxy), [urlfilter](https://github.com/Ozy-666/urlfilter) and [dnscrypt-proxy](https://github.com/Ozy-666/dnscrypt-proxy). They are archived, with their benchmarks kept for reference. Nothing changed for users: same addresses, blocking still on.

---

## How I work

- **Verify on real CPUs** — measured on production hardware, never guessed
- **Honest about results** — the dead-ends are documented alongside the wins
- **Privacy first** — nothing that could leak what you do is kept or sent anywhere
- **Always reversible** — every change can be switched off in one step

---

<sub>A public, no-logs DNS resolver for everyone — running at <a href="https://dnsdoh.art/">dnsdoh.art</a>. No telemetry, no logs.</sub>

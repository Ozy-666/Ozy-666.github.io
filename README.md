# Hi, I'm Ozy-666 👋

**I build free tools that make your internet private and fast.**

🛡️ **[DNSDOH.ART](https://dnsdoh.art/)** — my free service that blocks ads & trackers and keeps your browsing private
🌐 **[ozy-666.github.io](https://ozy-666.github.io/)** — my homepage

---

## What I made for you

**[DNSDOH.ART](https://dnsdoh.art/)** is a free, encrypted DNS service. In plain words, it does the "phone book" lookup your device makes every time you open a website — but it does it **privately and cleanly**:

- 🚫 **Blocks ads & trackers** — in every app, not just your browser
- 🔒 **Keeps you private** — your internet provider can't see which sites you visit
- ⚡ **Often makes pages faster** — less junk to load
- 🆓 **Free, no app, no logs** — nothing about you is ever recorded

It works on phones, computers, and routers — usually just **one setting**, no technical knowledge needed.

**→ [Set it up on your device](https://dnsdoh.art/setup.html)**

---

## Under the hood (for the technically curious)

You don't need any of this to use the service — but it's all open-source. I rewrote the core DNS software to be faster, leaner, and more private, and **every speed claim is backed by a real benchmark**, not a guess.

| Project | In plain words | Highlight |
|---------|---------------|-----------|
| **[AdGuardHome-edge-spec](https://github.com/Ozy-666/AdGuardHome-edge-spec)** | The brain of the service — stripped of anything that leaks data or wastes time | 24.6 MB build (−10 MB of bloat removed) |
| **[dnsproxy](https://github.com/Ozy-666/dnsproxy)** | How requests travel in and out — reuses connections, uses every CPU core | **+101%** more traffic handled under load |
| **[dnscrypt-proxy](https://github.com/Ozy-666/dnscrypt-proxy)** | Encrypts traffic on its way to the wider internet — slimmed and audited | **0** known vulnerabilities after audit |
| **[urlfilter](https://github.com/Ozy-666/urlfilter)** | Decides what's an ad or tracker — finds even tricky rules instantly | **248×** faster matching under attack |

**A favourite optimization — [Unbound on BoringSSL](https://github.com/Ozy-666/AdGuardHome-edge-spec#66-cryptographic-substrate--unbound-on-boringssl):** checking the security signatures that prove a website's address is genuine was eating nearly half the server's effort. I swapped in Google's faster, formally-verified math library (BoringSSL) to do that work — **−26% waiting per request, +9.6% more handled**, with a one-command undo kept ready.

---

## How I work

- **Verify on real CPUs** — measured on production hardware, never guessed
- **Honest about results** — the dead-ends are documented alongside the wins
- **Privacy first** — anything that could leak what you do is removed by default
- **Always reversible** — every change can be switched off in one step

---

<sub>Free, private internet for everyone — running in production at <a href="https://dnsdoh.art/">dnsdoh.art</a>. No telemetry, no logs.</sub>

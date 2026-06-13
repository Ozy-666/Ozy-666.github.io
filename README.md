# Edge Infrastructure & Low-Latency Network Architecture

Production-ready configurations, hardened deployment blueprints, and zero-allocation system optimizations for secure, high-concurrency edge routing.

## Operational Nodes
* **Production Resolver:** [DNSDOH.ART](https://dnsdoh.art) — Next-generation encrypted public DNS (DoH/DoT/DoQ) built on Unbound, BoringSSL, and optimized Nginx.
* **Architecture Dashboard:** [ozy-666.github.io](https://ozy-666.github.io) — Systems profile, core performance principles, and live node status.

## Core Tech Stack & Patches
* **Nginx 1.31 + BoringSSL (`fiat-crypto`):** Hardened TLS 1.3 transport layer, eliminating legacy cipher overhead.
* **Unbound:** Re-linked with BoringSSL to reduce CPU consumption during signed-flood DNSSEC validation.
* **Go DNS Filters:** Custom high-RPS rule-matching engines with sync.Pool buffer reuse to enforce zero-allocation hot paths.

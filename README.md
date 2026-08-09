<div align="center">

# 👻 Specter

### A fresh phone for every account

Per-app device identities that never repeat — so your accounts never get linked.

[**⬇️ Download APK**](../../releases/latest) · [How it works](#how-it-works) · [Setup](#setup) · [Get a key](#access) · [Full breakdown](#full-breakdown--how-specter-compares)

![Android 7–15](https://img.shields.io/badge/Android-7–15-3ddc84) &nbsp;![Root](https://img.shields.io/badge/root-Magisk%20%2B%20LSPosed-ffd54a) &nbsp;![Region](https://img.shields.io/badge/profiles-USA-e5736e)

<img src="docs/img/identity.png" width="290" alt="Specter — one tap applies an identity"/>
&nbsp;
<img src="docs/img/status.png" width="290" alt="Protection status — all green"/>

</div>

---

## What you get

- 🎭 **A different device per app** — give every account its own phone identity, applied in one tap.
- 🔒 **Never reused** — every identity is unique and internally consistent, so nothing links your accounts.
- 🧪 **Built-in IP reputation check** — test your proxy/exit IP for fraud, VPN, and blacklist flags *before* you sign up.
- 💾 **Fingerprint vault** — save any identity and reload it anytime.
- 📲 **Save & restore logins** — keep your logged-in sessions and switch between them without signing in again.
- 🌍 **Timezone follows your proxy** — the device clock matches your exit location automatically.
- ✅ **Proof it worked** — a built-in check reads back what each app actually sees.
- ⚡ **One-tap setup** — installs everything and gets you running.
- 🕵️ **Yours alone** — works offline, no account, no phone-home.
- 🦅 **Realistic US profiles** — real device models paired with US carriers.

## How it works

**1.** Open a target app on a fresh, unique device identity. → **2.** Save the login. → **3.** Switch identity for the next account — the previous session is safely vaulted and restorable.

Every account signup sees a different phone. Nothing carries over to link them.

## Specter Lite — free, no root

Not rooted? **[Specter Lite](../../releases/latest)** is a free companion app that reads your device's real fingerprint (every identifier an app can see without root) and shows it in one place — so you know exactly what your phone looks like to the apps you use. No spoofing, no root, no key required. The full Specter (above) is what rotates that fingerprint per account.

## Setup

1. A rooted Android phone (Magisk + Zygisk + LSPosed).
2. Install the [latest APK](../../releases/latest).
3. Open Specter → **Set up everything** → reboot.
4. Enter your key on the **Activation** screen.
5. Randomize → Apply. Done.

## Access

Keys are device-bound and come in **1 day · 1 week · 2 weeks · 1 month · permanent**. Contact the operator for a key.

---

<details>
<summary><b>Full breakdown &amp; how Specter compares</b></summary>

### Why

Identifier spoofers that reuse a value get you linked and banned. The tools that came before left most of the hardware **real** and rotated only a handful of IDs — so a fraud stack could still fingerprint the untouched signals and tie the accounts together.

Specter's one rule: **no identifier is ever reused, and the whole device reads coherent.** The Build fields match the model, the IMSI matches the SIM carrier, US devices pair with US carriers. An incoherent device is itself a flag — so Specter never ships one.

### What makes it different

- **Two injection layers, both proven on-device.** Specter spoofs on *both* the app layer and the layer beneath it, in lockstep — so a signal read the "deep" way is covered too. Tools that only cover the app layer leak the moment something looks lower.
- **Coherent, US-market profiles from 499 real devices.** Every field is made to match one real device, top to bottom — not a random mix that flags as fake.
- **Full identifier set, per app** — the complete set of device IDs an app can read, all fresh and consistent.
- **Never-reused, enforced.** A race-safe ledger guarantees uniqueness (5000+ generations, zero collisions) — not "should be unique," *guaranteed* unique.
- **Timezone follows the proxy, not the phone** — auto-aligned to your exit IP, never your home IP.
- **Read it back — don't trust the tool.** A built-in probe reads what the target app *actually* stored and shows a per-field ✅/❌.
- **One-tap setup** — installs everything and reboots, from inside the app.

### How Specter compares

| | **Specter** | GeerGit | byedentity | Mirage\* |
|---|:---:|:---:|:---:|:---:|
| Two-layer (app **+** deep) spoof | ✅ proven | app-mostly | deep only | app only |
| Hardware coherence (model/chip/RAM/board) | ✅ enforced | ⚠️ leaves HW real | ❌ left real | not verified |
| Both SIM slots + full telephony | ✅ | partial | ❌ | not verified |
| Widevine → L3 | ✅ (no root for the spoof) | ❌ | ✅ (needs root) | not verified |
| Never-reused guarantee | ✅ enforced ledger | ⚠️ manual / increment | n/a | not verified |
| USA-coherent values | ✅ full | partial | ❌ | not verified |
| Works offline / no server leash | ✅ stateless | ✅ | ❌ phone-home + kill-switch | ❌ login + cloud |
| On-device read-back verification | ✅ probe | ❌ | ❌ | ❌ |

<sub>\*Mirage: capabilities not independently verified — it ships a login + cloud backend (a server leash), which Specter deliberately avoids. GeerGit/byedentity cells sourced from decompile analysis. Specter deliberately rejects a remote kill-switch / phone-home: a phone-home is itself a signal.</sub>

### Honest limits

- **Root required** (Magisk + Zygisk + LSPosed). This is a power tool, not a one-tap app-store install.
- Specter makes every **identifier** fresh, coherent, and verified-spoofed, and closes the gaps that get accounts linked — but it isn't magic, and it's one layer of the picture.
- The **network** layer (proxy quality, datacenter-IP reputation) is your proxy's job — which is exactly why the IP reputation check is built in.

<sub>USA device profiles · Android 7–15 (minSdk 24) · brands: Google · Motorola · Samsung · LGE</sub>

</details>

<div align="center">
  <img src="assets/avatar.png" width="140" alt="Vincent Fox Vibe-Junior" />
  <h1>Vincent&nbsp;Fox</h1>
  <p><b>agent tooling · self-hosted infrastructure · full-stack</b><br/>
  <sub>TypeScript · Python · Kotlin</sub></p>
  <sub><b>English</b> · <a href="README.ru.md">Русский</a></sub>
</div>

```console
$ whoami
vincentfox — I build the tooling that lets me run a fleet of coding agents from a
phone, and I host every service that tooling depends on myself.

$ systemctl status homelab --no-pager
● homelab.target - active (running), 24/7
   nodes    thor1   mini-PC · Ubuntu 24.04 · agents, gateway, PTY panes
            srv78   VPS     · Debian      · nginx edge, relay, RustDesk, tunnels
            de5     edge    · tunnel terminator for the phone endpoint
            bigpc   5700X + RTX 3070 · llama.cpp, local models
   wires    WireGuard · ZeroTier · reverse-SSH user units (self-healing, BatchMode)
   edge     nginx SNI routing → anytls · naive · hysteria2 with port hopping
   memory   Mnemopi banks + project graph, every claim carries a source

$ tail -n 2 /var/log/focus.log
  agent remote for the phone: Bun gateway, React PWA, update engine with rollback
  rule: "done" means verified by a real run, never by a plausible report
```

## Building

| project | what it is |
|---|---|
| **OMP Pocket** <sub>`private`</sub> | Remote for an [omp](https://www.npmjs.com/package/oh-my-pi) agent fleet from a phone. React PWA + Bun gateway (session registry, attachments, search, push, autonomous tasks); E2E collab relay over AES-256-GCM; PTY pane runtime with screen emulation and restore-after-restart; update engine that verifies SHA-256, installs atomically and rolls back on its own, with a chaos suite over the failure paths. 42k lines of TypeScript (52k with styles), 30 test files. |
| **my-cinema** <sub>`private`</sub> | Android TV client in Kotlin — modular Gradle (core / feature / app), own design layer, benchmarks before feature work. |
| **catalogue feed** <sub>`private`</sub> | Python: a 2,161-item catalogue crawled, filtered and assembled into a strict YML feed for Yandex Direct — price, stock, category, and at least four white-background photos per item — plus a selection report naming the reason every dropped item fell out. |
| **homelab** | Debian VPS + Ubuntu mini-PC: nginx edge with SNI routing, systemd units, WireGuard/ZeroTier mesh, self-hosted RustDesk, llama.cpp serving local models to the agents. |

## Stack

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Bun](https://img.shields.io/badge/Bun-000000?style=flat-square&logo=bun&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)
![Debian](https://img.shields.io/badge/Debian-A81D33?style=flat-square&logo=debian&logoColor=white)
![nginx](https://img.shields.io/badge/nginx-009639?style=flat-square&logo=nginx&logoColor=white)
![systemd](https://img.shields.io/badge/systemd-333333?style=flat-square&logo=systemd&logoColor=white)
![WireGuard](https://img.shields.io/badge/WireGuard-88171A?style=flat-square&logo=wireguard&logoColor=white)
![Caddy](https://img.shields.io/badge/Caddy-1F88C0?style=flat-square&logo=caddy&logoColor=white)
![llama.cpp](https://img.shields.io/badge/llama.cpp-GGUF-black?style=flat-square)

## Now

- **OMP Pocket** — the workflow tree (`WORKFLOW.md` → steps → subtasks) and the memory graph, so an agent keeps the provenance of what it claims.
- **Harness rules that bite** — hooks, not paragraphs: no edits before a plan, no status line without a real run, loops cut after the third identical failure.

<sub>Everything here is built to be read six months later: no shims, no “temporary” layers, no dead branches.</sub>

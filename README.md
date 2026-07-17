<h1 align="center">Sepehr Safari</h1>

<p align="center">
  <strong>Software engineer building open-source eMobility DevTools, native protocol libraries, and AI-native engineering workflows.</strong>
</p>

<p align="center">
  <a href="https://ocppdebugkit.com">OCPP DebugKit</a>
  ·
  <a href="https://github.com/open-ocpp-trace/specification">Open OCPP Trace</a>
  ·
  <a href="https://github.com/sepehr-safari/ocpp-handbook">OCPP Handbook</a>
  ·
  <a href="https://zignostr.com">zig-nostr</a>
  ·
  <a href="https://www.linkedin.com/in/sepehrsafari/">LinkedIn</a>
</p>

---

I’m a full-stack software engineer with 7+ years of experience building developer tools, web applications, open-source infrastructure, and SaaS products.

My current work sits at the intersection of **eMobility**, **developer tooling**, **protocol engineering**, **product intelligence**, and **AI-native engineering workflows**.

I care about making complex systems easier to inspect, understand, and improve.

## eMobility & OCPP

### [OCPP DebugKit](https://ocppdebugkit.com)

> Open-source DevTools for debugging OCPP charging sessions.

[![toolkit](https://img.shields.io/github/v/release/ocpp-debugkit/toolkit?display_name=tag&label=toolkit)](https://github.com/ocpp-debugkit/toolkit/releases)
[![npm](https://img.shields.io/npm/v/@ocpp-debugkit/toolkit?label=npm)](https://www.npmjs.com/package/@ocpp-debugkit/toolkit)
[![studio](https://img.shields.io/github/v/release/ocpp-debugkit/studio?display_name=tag&label=studio)](https://github.com/ocpp-debugkit/studio/releases)
[![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](https://github.com/ocpp-debugkit/toolkit/blob/main/LICENSE)

OCPP DebugKit helps charging-infrastructure developers diagnose failures and understand what happened during an OCPP session. It is two independent products that share one trace format:

| | Language | Surface | Role |
|---|---|---|---|
| [**toolkit**](https://github.com/ocpp-debugkit/toolkit) | TypeScript | npm · CLI · web inspector | Parse, analyze, and report traces anywhere, including CI |
| [**Studio**](https://github.com/ocpp-debugkit/studio) | Zig | native desktop app | Live capture off the wire, native performance, OS integration |

The two share **no code**. They meet at a conformance contract (the same trace format, the same event model, the same 16-rule failure taxonomy), with Studio’s goldens generated from the toolkit’s evaluator and re-checked in CI on every change.

- Inspect charging-session traces, timelines, and individual messages
- Detect authorization, connector, and connectivity failures (16 rules, 15 scenarios)
- Proxy a live charge point ↔ CSMS session and flag failures as they stream (Studio)
- Generate shareable Markdown and HTML reports; diff and anonymize traces
- Analyze traces in a browser, a CLI, or a native app, keeping trace data local

*Status: both products are pre-1.0 and shipping, the toolkit on npm and Studio as a native macOS and Linux build.*

**Explore the project**

[Web Inspector](https://ocppdebugkit.com/inspector) · [Documentation](https://ocppdebugkit.com/docs) · [toolkit](https://github.com/ocpp-debugkit/toolkit) · [Studio](https://github.com/ocpp-debugkit/studio) · [npm](https://www.npmjs.com/package/@ocpp-debugkit/toolkit)

---

### [Open OCPP Trace](https://github.com/open-ocpp-trace/specification)

> A vendor-neutral format for recording OCPP message exchanges.

Open OCPP Trace is a versioned, implementation-independent JSON/JSONL format for OCPP traffic. It gives producers (simulators, proxies, charging stations, CSMS) and consumers (analyzers, debuggers, CI pipelines) one shared record to write to and read from, so a captured session can be replayed, diffed, or filed as a reproducible bug report by anyone. The format lives in its own neutral repository so no single project’s roadmap governs it.

It grew out of an ongoing collaboration with the maintainers of [ocpp-cp-simulator](https://github.com/shiv3/ocpp-cp-simulator) and [awesome-ev-charging](https://github.com/juherr/awesome-ev-charging). DebugKit’s toolkit already reads and writes the format, and I’m contributing the JSON Schema and a conformance suite so independent implementations can be checked against the same fixtures.

[Specification](https://github.com/open-ocpp-trace/specification)

---

### [OCPP Handbook](https://github.com/sepehr-safari/ocpp-handbook)

> A free, vendor-neutral course on EV-charging software.

The OCPP Handbook starts from zero and builds toward reading raw OCPP frames, running your own captures, and working with the specifications directly: industry context first, then the hardware and physical layer, then the protocol stack, then field debugging. Claims link to their sources, and protocol statements cite the specifications by section.

It is written in the open and still in progress, with the early modules available now.

[Read the handbook](https://github.com/sepehr-safari/ocpp-handbook)

## Also building

### [zig-nostr](https://zignostr.com)

> The Nostr protocol, natively in Zig.

[![nostr](https://img.shields.io/github/v/release/zig-nostr/nostr?display_name=tag&label=nostr)](https://github.com/zig-nostr/nostr/releases)
[![signet](https://img.shields.io/github/v/release/zig-nostr/signet?display_name=tag&label=signet)](https://github.com/zig-nostr/signet/releases)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/zig-nostr/nostr/blob/main/LICENSE)

A foundational Nostr protocol library for Zig: keys and signatures, events, relay transport with the outbox model, a zero-copy local-first event store, and NIP-46 remote signing. Plus [Signet](https://github.com/zig-nostr/signet), a native remote signer that keeps your key off every client and holds every request for explicit approval.

- secp256k1 keys and BIP-340 Schnorr signatures via `libsecp256k1`, passing the official test vectors (19/19)
- A zero-copy, memory-mapped LMDB event store whose own benchmark measures ~0.28 ms feed queries that stay flat as the store grows
- NIP-65 outbox routing with zero hardcoded relays, NIP-44 v2 encryption, and NIP-42 relay auth

*Status: `nostr` is pre-alpha (`v0.3.5`); Signet is early and macOS-only. Both ship tested releases, but APIs may still change before 1.0.*

[Docs & benchmarks](https://zignostr.com) · [nostr](https://github.com/zig-nostr/nostr) · [Signet](https://github.com/zig-nostr/signet)

---

### [ProductCue](https://productcue.ai)

> AI-native product intelligence for early-stage software teams.

ProductCue turns public market evidence (competitor reviews, recurring complaints, pricing friction, feature gaps) into prioritized opportunities and build briefs, so teams can decide what is worth building before they build it.

## Selected open-source work

I’ve been building on Nostr since 2023, first in TypeScript, where the work included developer libraries, project scaffolding, protocol-based applications, and two OpenSats grants. `zig-nostr` above is that same protocol, rebuilt native.

| Project | Description |
|---|---|
| [`nostr-hooks`](https://github.com/ostyjs/nostr-hooks) | React hooks for building applications on the Nostr protocol |
| [`create-osty`](https://github.com/ostyjs/create-osty) | Project scaffolding for quickly starting Nostr applications |
| [`Pinstr`](https://github.com/sepehr-safari/pinstr) | Open-source social platform for curating and sharing interests |
| [`Nostribe`](https://github.com/sepehr-safari/nostribe) | Twitter-style social application built on Nostr |
| [`NIP-29 Groups`](https://github.com/max21dev/groups) | Group-chat client built around the NIP-29 specification |

## Engineering focus

- Developer tools and debugging infrastructure
- Protocol-oriented and event-driven systems (OCPP, Nostr)
- Native, local-first, privacy-conscious software
- Full-stack TypeScript product development
- AI-native product and engineering workflows

## Technologies

**Primary stack**

`TypeScript` · `React` · `Next.js` · `Node.js` · `Tailwind CSS`

**Native and systems**

`Zig` · `Native SDK` · `LMDB` · `libsecp256k1`

**Data and infrastructure**

`PostgreSQL` · `Supabase` · `Redis` · `SQLite` · `IndexedDB`

**Additional experience**

`Python` · `Go`

**AI workflows**

LLMs · customized AI agents · multi-agent orchestration · engineering automation

## How I work

I prefer software that is:

- Useful before it is impressive
- Explicit rather than unnecessarily abstract
- Built around real evidence and user pain
- Easy for other developers to understand and extend
- Honest about what it currently supports

AI has made building faster, but speed is only valuable after choosing the right problem.

## Let’s connect

I’m interested in collaborating with eMobility and EV-charging engineers, OCPP implementers and CSMS teams, open-source maintainers and contributors, and developers working on protocol tooling or practical AI-native workflows.

For OCPP DebugKit feedback, bugs, or feature requests, please [open an issue](https://github.com/ocpp-debugkit/toolkit/issues).

You can also find me on:

[LinkedIn](https://www.linkedin.com/in/sepehrsafari/) · [Personal Website](https://sepehrsafari.com) · [ProductCue](https://productcue.ai)

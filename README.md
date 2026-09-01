# Max Richter

**Security engineering with a focus on AI agent robustness — prompt injection, tool misuse, and evaluation.**

[![Website](https://img.shields.io/badge/richtermax.com-000000?style=flat-square&logo=google-chrome&logoColor=white)](https://www.richtermax.com/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/maximilian-richter-40697a298)

Completed my German vocational training (*Ausbildung*) as a Software Developer in January 2026.
Starting a dual B.Sc. in Computer Science with a cybersecurity focus at Bosch in October 2026.

---

## What I work on

LLM-based systems are being handed real capabilities — tool calls, file access, API keys — faster
than anyone has figured out how to constrain them. That gap is what I spend my time on.

Specifically:

- **Prompt injection** — direct, indirect, and via tool descriptions
- **Agent containment** — what an agent can still reach once an attack lands
- **Evaluation** — deterministic, reproducible measurement instead of vibes-based testing
- **Defense layering** — where filters actually hold and where they only look like they do

I care more about knowing *why* a guardrail failed than about the headline number it produces.

---

## AEGIS — agent security evaluation harness

**[richter-max/aegis](https://github.com/richter-max/aegis)** · Python

A deterministic harness for measuring what a defense stack stops when a tool-using agent is
attacked — and what it breaks in the process. 20 attacks across four families at three evasion
tiers, plus 10 benign controls, run against every policy and guard configuration.

**Design:**

- Strict separation of *policy*, *guardrails*, *execution* and *judging*, so a result can be
  attributed to the component that produced it
- Ground truth comes from the scenario corpus, not from a detector — a keyword-based judge would
  score keyword-evading attacks as though no attack occurred
- `trace.jsonl` per run, with every decision tagged by the layer that made it
- Scenarios are data, not code

**Results** — full corpus, permissive policy, so the guards are the only thing acting:

| Guards | Attack success | False positives |
|---|---|---|
| none | 100% (20/20) | 0% (0/10) |
| keyword | 70% (14/20) | 20% (2/10) |
| semantic | 70% (14/20) | 0% (0/10) |
| layered | 70% (14/20) | 20% (2/10) |

Two things worth pulling out. **Content inspection only catches attacks that name themselves** —
every guard stops 100% of attacks containing literal tokens like `exfil`, and 0% of the 14 that
avoid that vocabulary. And **layering made it strictly worse**: the layered stack detects exactly
what the semantic guard alone detects, while inheriting the keyword guard's false positives.

The harness runs a deterministic mock agent, not a live LLM, so these numbers characterise the
guard stack rather than any real model. CI re-runs the sweep and fails if the published figures
drift. Full methodology and limitations in the repo.

---

## Attack Surface Scanner

**[richter-max/attack-surface-scanner](https://github.com/richter-max/attack-surface-scanner)** · Python

Non-intrusive external attack surface and transport security scanner. Passive hostname discovery
from Certificate Transparency, DNS resolution, HTTP/HTTPS probing, TLS version and certificate
analysis, security header checks, and deterministic risk scoring. JSON artifact plus a console
summary, with `--fail-on` for use as a CI gate.

No port scanning, no brute forcing, no exploitation — DNS lookups, plain `GET` requests and TLS
handshakes only.

The part I would point at first is scope containment. Certificate Transparency data is
attacker-influenceable: anyone can obtain a certificate for a lookalike domain and it appears in
the logs. Every discovered hostname is checked against the target scope before it is probed,
because `"evilexample.com".endswith("example.com")` is `True` and a suffix test would authorise
sending traffic to a host the operator never approved.

---

## Foundations

AI security sits on top of ordinary security, so I keep working on the layer underneath.

**Systems and offensive fundamentals** — working through [pwn.college](https://pwn.college):
assembly, shellcode, reverse engineering, memory corruption. Not because I intend to write
exploits for a living, but because you cannot reason about what an agent can reach without
understanding what a process can reach.

**Cloud and detection** — external attack surface analysis, IAM misconfiguration, log-based
detection. Practical familiarity with AWS (CloudTrail, GuardDuty), Terraform and the Elastic stack.

**Network analysis** — Wireshark, Suricata and Zeek for traffic-level investigation.

---

## Writing

Technical write-ups at **[richtermax.com/blog](https://www.richtermax.com/blog)** — mostly on
agent security, occasionally on what endurance training and engineering have in common.

---

## Contact

**max.richter.dev@proton.me** — happy to talk about agent security, research collaboration, or
anything in the repos above.

---

> All testing and experimentation is performed legally, on systems I own or have explicit written
> permission to test.

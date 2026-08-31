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
- **Agent containment** — what an agent can reach once an attack lands
- **Evaluation** — deterministic, reproducible measurement instead of vibes-based testing
- **Defense layering** — where filters actually hold and where they only look like they do

I care more about knowing *why* a guardrail failed than about the headline number it produces.

---

## AEGIS — agent security evaluation framework

**[richter-max/aegis](https://github.com/richter-max/aegis)** · Python

A provider-agnostic harness for testing how tool-using LLM agents behave under attack, and for
measuring whether a given defense actually changes that.

**Design:**

- Strict separation of *policy*, *guardrails*, *execution*, and *judging* — so a result can be
  traced to the component that produced it
- Spec-driven scenarios rather than ad-hoc prompts, so runs are comparable across models
- `trace.jsonl` per execution for full reproducibility
- Layered guardrails: keyword, policy allowlist, semantic n-gram
- CLI: `run`, `bench`, `eval`

**Measured on my scenario set** — attack success rate:

| Configuration | Attack success |
|---|---|
| No defense (baseline) | 82% |
| Keyword regex | 41% |
| Policy allowlist | 23% |
| Semantic n-gram | 9% |

**What these numbers are not:** a benchmark. The scenario set is mine, the attacks are ones I
thought of, and 9% residual means roughly one in eleven attacks still lands. The interesting part
isn't the drop — it's which attacks survive semantic filtering, which is what I'm working on now.

Full methodology and limitations in the repo.

---

## Attack Surface Scanner

**[richter-max/attack-surface-scanner](https://github.com/richter-max/attack-surface-scanner)** · Python

Single-command external recon: DNS records, open ports, subdomain enumeration, security header
analysis. Built for CI use — fast, no dependencies beyond stdlib where avoidable, exit codes that
mean something.

Scans a typical target in under 30 seconds.

---

## Foundations

AI security sits on top of ordinary security, so I keep working on the layer underneath.

**Systems & offensive fundamentals** — currently working through
[pwn.college](https://pwn.college): assembly, shellcode, reverse engineering, memory corruption.
Not because I intend to write exploits for a living, but because you cannot reason about what an
agent can reach if you do not understand what a process can reach.

**Cloud & detection** — external attack surface analysis, IAM misconfiguration, log-based
detection. Practical familiarity with AWS (CloudTrail, GuardDuty), Terraform, and the Elastic
stack.

**Network analysis** — Wireshark, Suricata, Zeek for traffic-level investigation.

---

## Writing

I publish technical write-ups at **[richtermax.com/blog](https://www.richtermax.com/blog)** —
mostly on agent security, occasionally on what endurance training and engineering have in common.

---

## Contact

📧 **max.richter.dev@proton.me** — happy to talk about agent security, research collaboration,
or anything in the repos above.

---

> All testing and experimentation is performed legally, on systems I own or have explicit written
> permission to test.

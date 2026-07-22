# Claude AI Fluency: Exercise 2 - Exploring a Familiar Topic
**Course/Module:** AI Fluency: Framework & Foundations (Anthropic Academy)  
**Objective:** Engage in a natural conversation with Claude about a familiar technical domain (homelab architecture & network security) to observe how domain expertise enables real-time discernment and output evaluation.

---

## 1. Core Concepts & Methodology
- **Domain-Driven Discernment:** Utilizing personal expertise to critically evaluate AI responses, quickly spotting oversimplifications, logic gaps, or configuration edge cases.
- **Collaborative Augmentation:** Using the LLM as a sounding board to brainstorm deployment architectures while maintaining human ownership over technical decisions.
- **Real-Time Calibration:** Refining model outputs through immediate, targeted corrections when initial suggestions don't match specific operational constraints.

---

## 2. Prompt Iteration & Engineering

### Baseline / Naive Prompt
```text
Tell me how to set up VLANs and local services in a homelab.

```

### Engineered Prompt (Applied Context & Constraints)

```text
<system_role>
You are a Network Engineer and Systems Administrator specializing in self-hosted infrastructure.
</system_role>

<context>
I maintain a local homelab running Proxmox VE and Docker. I am restructuring my internal network to isolate untrusted IoT devices, media services, and core management infrastructure into separate VLANs.
</context>

<task>
Let's talk through an optimal subnetting and VLAN tag structure for this setup. Suggest a clean, standard layout for:
1. Management / Hypervisor layer
2. Internal trusted devices & containers
3. Isolated IoT segment
4. Guest / DMZ network

Provide a brief rationale for the firewall boundaries between these segments.
</task>

<constraints>
Keep the discussion grounded in standard RFC 1918 private IPv4 addressing (e.g., 10.x.x.x or 192.168.x.x). Ask me one clarifying question about my current router/firewall hardware before diving into complex routing rule suggestions.
</constraints>

```

---

## 3. Execution & Output Verification

### Output Analysis & Discernment Notes

* **Enhancing Thinking:** Claude provided a clean, industry-standard 10.0.X.0/24 subnet mapping scheme that logically grouped tags (e.g., VLAN 10 Management, VLAN 20 Trusted, VLAN 30 IoT).
* **Domain Evaluation:** Claude recommended setting up inter-VLAN routing directly on the layer-2 virtual bridges in Proxmox. Having experience with container networking, I recognized this would bypass firewall controls and require routing through the dedicated upstream firewall (e.g., OPNsense) instead.
* **Course Correction:** I prompted Claude to adjust the design so that all inter-VLAN traffic passes through the primary gateway interface, enforcing strict stateful inspection across subnets.

---

## 4. Key Takeaways & Best Practices

| Concept / Technique | Practical Application |
| --- | --- |
| **Expert-Led Discernment** | High domain knowledge allows instant spotting of flaws (like open inter-VLAN paths) before applying generated configurations. |
| **Constraint Injection** | Instructing the model to ask a clarifying question prevents it from making wrong assumptions about hardware or network topology. |
| **Iterative Refinement** | Treat the first response as a baseline draft; use direct follow-up prompts to align the solution with your exact setup. |

```

```

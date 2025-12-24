# Critical Variable Watchdog: Hardware-Speed AI Safety Monitoring

A proposal for using fast, simple binary neural networks as independent security monitors for AI systems.

## Problem

AI systems controlling physical devices (drones, robots, autonomous vehicles) have critical variables that, if manipulated, cause catastrophic outcomes:

- Enemy/ally classification flags
- Target coordinates
- Authorization signals
- Safety boundaries

Attacks on AI systems—whether through adversarial inputs, concept manipulation, or prompt injection—ultimately must affect these variables to cause harm. But complex AI systems process information through many layers, giving attacks time to propagate.

## Core Idea

**Use the speed asymmetry between attack and defense.**

| Attack | Defense (Binary Watchdog) |
|--------|---------------------------|
| Inject manipulation | Monitor input patterns |
| Propagate through model layers | Detect variable anomalies |
| Affect critical output | **Shut down BEFORE this step** |

A binary neural network (weights = +1 or -1 only) implemented on FPGA can run inference in **nanoseconds**—orders of magnitude faster than the complex AI it monitors. This speed advantage means the watchdog can detect and respond to anomalies before they take effect.

## Why Binary Models Work Here

| Property | Security Benefit |
|----------|------------------|
| Extreme simplicity | Smaller attack surface, easier to verify |
| Hardware implementation | Can't be disabled by software attacks |
| Independence | Separate from main AI system |
| Speed | Intervenes before damage occurs |

The watchdog doesn't need to be smart. It only needs to answer: "Do these critical variables look normal?"

## Architecture

```
┌─────────────────────────────────────────────────┐
│              Main AI System                      │
│  (Complex model - LLM, vision, planning, etc.)  │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼ Critical Variables
┌─────────────────────────────────────────────────┐
│         Binary Watchdog (FPGA)                  │
│  - Monitors: coordinates, flags, auth signals   │
│  - Checks: pattern consistency, value bounds    │
│  - Response: μs-scale shutdown trigger          │
└─────────────────┬───────────────────────────────┘
                  │
                  ▼ Pass / Kill Signal
┌─────────────────────────────────────────────────┐
│              Physical Actuators                  │
└─────────────────────────────────────────────────┘
```

## Connection to Distributed Resilience

This watchdog concept integrates with broader AI security through cognitive diversity:

**Layer 1: Distributed Verification (slow, thorough)**
Multiple AI systems with different architectures cross-check each other's outputs. Different "worldviews" catch different failure modes.

**Layer 2: Critical Variable Watchdog (fast, focused)**
Hardware-speed last line of defense. When distributed verification is too slow, the watchdog provides reflexive protection.

Like biological systems:
- Immune system = distributed, adaptive, slow
- Reflex arc = simple, hardwired, fast

Both are necessary.

## Related Work

Existing research provides building blocks but not this specific integration:

- **FPGA Binary NNs**: LogicNets achieves <15ns inference (Umuroglu et al., 2020)
- **Neural Simplex Architecture**: Independent safety monitors with override (Phan et al., 2020)
- **Control Barrier Functions**: Formal methods for critical variable specification
- **Small model supervision**: LlamaGuard (7B) monitors larger models

**Gap**: No existing work combines hardware-implemented learned monitors specifically for detecting AI manipulation of physical system variables.

## Open Questions

1. How to define "normal" for learned systems whose behavior is inherently variable?
2. What's the minimum set of critical variables that covers most attack vectors?
3. How to prevent the watchdog itself from being targeted during training?
4. Can watchdogs be standardized across different AI architectures?

## Origin

This concept emerged from a conversation analyzing [Tebasaki_lab's FPGA binary neural network research](https://x.com/Tebasaki_lab) and connecting it to prior work on [Distributed Resilience Systems Based on AI Identity](https://github.com/kj-keijima/ai-identity-security).

The insight: if binary models can run at 500M fps, they can monitor critical variables faster than any attack can propagate through a complex AI system.

---

*December 2025*

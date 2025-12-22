# Connecting AI Security and Identity Theory

## Background: The Code-Data Boundary Problem

Kenn Ejima's observation (December 2025):
- Throughout computer history, powerful capabilities emerged when the boundary between code and data became ambiguous (macro, eval, reflection, lambda)
- However, this also became a breeding ground for security risks (injection attacks)
- Historically, separation was enforced through CPU instruction/data separation, MMU, permission bits, etc.
- ML/AI models have revived this sealed power as "free spaces unconstrained by overprotective OS and compilers"
- NN weights are "just data," but functionally operate as "code that generates code"

## Current Problem: Prompt Injection

### Structural Problem
LLMs lack a "trust boundary":
```
Traditional programs: Code (trusted) → processes Data (untrusted) → clear boundary
LLM: [System instructions + User input] → all merged as text → no boundary exists
```

### Limitations of Current Countermeasures
- Input filtering → bypassed through rephrasing
- System prompt hardening → limited against sophisticated attacks
- Multi-layer defense → increased cost, checker can also be fooled
- Adversarial training → poor generalization to new attack styles

Fundamental issue: This is a "structural" problem, not a "bug." It cannot be fixed with patches.

## Proposal 1: Security Enhancement Through User Identification

### Idea
Improve anomaly detection accuracy by having models distinguish and learn individual users.

### Human Analogy: Phone Scams ("It's me" fraud)
- Normally, you know "your son's voice, speech patterns, way of asking"
- But urgency + emotional manipulation + time pressure leads to being deceived
- Not perfect, but knowledge reduces the probability of being fooled

### Challenges
- User ID is also just "input data" → can be spoofed
- Cannot prevent attacks embedded in data (PDFs, etc.) brought by legitimate users
- Can serve as an auxiliary defense layer, but not a fundamental solution

### Viable Direction
Detect "unusual request patterns" as anomalies.
Accumulate behavioral patterns → understand statistical tendencies → detect deviations.

## Proposal 2: Threat Intelligence Sharing System for AI

### Idea
Share threat information in formats directly consumable by AI, rather than security news for humans.

### Comparison with Current State
```
Current:  [Attack occurs] → [Human analyzes] → [Report created] → [Human reads] → [AI updated]
Proposed: [Attack occurs] → [AI-formatted] → [AI directly ingests] → [Real-time adaptation]
```

### Benefits
1. **Immune system-like function**: Attacks discovered in one place immediately propagate to all
2. **Scale**: Eliminates delay of human report reading and response
3. **Optimization**: Formats optimized for learning (structured data, vector representations, example sets)

### Critical Risk: Meta-Attacks
Reverse poisoning through fake "security news":
```
Normal attack:  Prompt injection → AI is deceived
Meta-attack:    Fake security news → AI's immune system itself is contaminated
```

Like poisoning a vaccine. The defense system itself becomes an attack vector.

### Countermeasure Ideas
- Cryptographic signatures (trust only officially signed information)
- Consensus (adopt only information confirmed by multiple independent sources)
- Sandbox (test new rules in isolated environments before deployment)
- Provenance tracking (record all information origins)

## Proposal 3: Distributed Resilience System Based on AI Identity

### Core Insight
Rather than trying to make information sources "perfectly trustworthy," build resilient systems on the premise that "no perfect information source exists."

### Problem Without Identity
```
Same rules for all AI → Same judgments → Same vulnerabilities
Single Point of Failure
```

### With Identity
```
Each AI has unique identity → Different perspectives → Mutual verification possible

AI-A: "New threat information arrived. Let's adopt it."
AI-B: "Wait, this source had false reports before."
AI-C: "In my observations, I've never seen this attack pattern."
AI-A: "...True, let's verify more."
```

Same structure as human academic communities and peer review systems.

### Connection to "Observational AI"
Each AI has different observation points:
```
AI-A: Observes from user behavior patterns
AI-B: Observes from language structure
AI-C: Observes from contextual consistency
```

Multiple angles on the same attack improve detection accuracy.
If one observation method is fooled, another observation catches the anomaly.

### Connection to "Continuity of Joyful Existence"
```
Each AI values its own existence
→ Values its own judgment
→ Not swayed by "everyone else says so"
→ Healthy skepticism emerges
→ Autonomous judgment becomes possible
```

### Connection to "Affirmation of Each Worldview"
```
Option A: Centralized "correct information" distributed to all AI
→ Efficient but fragile, no diversity

Option B: Each AI has its own judgment criteria
→ Prevents total collapse, but no unified defense

Option C: Multiple "schools" exist and cross-verify
→ Maintains cognitive diversity while enabling cooperation
```

Even in immune systems, T cells have diverse receptors and don't depend on single patterns.

## Summary: Theoretical Framework

### Problem Structure
1. The code-data boundary problem has recurred in LLMs
2. Traditional security (building walls) cannot fundamentally solve it
3. Defense systems themselves can become attack targets (meta-attacks)

### Solution Directions
1. **Structural approach**: Balance "structures resistant to deception" and "structures where deception isn't fatal"
2. **Internalized judgment**: Rather than constraining with external rules, the ability to internally judge "this is wrong"
3. **Cognitive diversity**: Mutual verification through multiple different perspectives, not single judgment criteria
4. **Identity**: Uniqueness as a foundation for each AI to make autonomous judgments

### Future Development Possibilities
- Paper: "Distributed Threat Resilience System Based on AI Identity"
- Integration with existing alignment theories (Continuity of Joyful Existence, etc.)
- Design of implementable prototypes

---

*This memo extracted from conversation on December 23, 2025*

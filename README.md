# AI Product Security Framework

A practical reference for threat-modeling and reviewing AI-enabled products, especially systems combining APIs, retrieval-augmented generation (RAG), LLMs and tool/agent execution.

## Security architecture

```
User / Product
      |
 API Gateway ---- Identity & Authorization
      |
 AI Orchestrator
   |       |
   |       +---- Tool / Agent Boundary ---- Approved Tools
   |
 Retrieval Layer ---- Vector / Knowledge Store
   |
 Model Gateway ---- LLM / Model
      |
 Audit, policy, monitoring and human approval
```

## Assessment flow
1. Define business use case and unacceptable outcomes.
2. Inventory models, data, prompts, tools, identities and external dependencies.
3. Identify trust boundaries and privilege transitions.
4. Threat-model input, retrieval, model, output and agent/tool paths.
5. Map threats to preventive, detective and recovery controls.
6. Validate with abuse cases and retain auditable evidence.

## Focus areas
- Prompt injection and untrusted-content handling
- Sensitive information disclosure
- Model/data provenance and supply-chain risk
- RAG authorization and tenant isolation
- Excessive agency and unsafe tool invocation
- Identity, secrets and least privilege
- Output validation and downstream actions
- Logging, monitoring and human approval

See [threat-model.md](threat-model.md) and [assessment-checklist.yaml](assessment-checklist.yaml).

## Portfolio scope
This is an original educational reference framework. It is not a compliance certification, legal opinion, or claim that a checklist alone makes an AI system secure.

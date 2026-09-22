# AI Product Threat Model

## Assets
User data, system prompts, credentials, retrieval corpus, model configuration, tool permissions, model outputs, audit evidence and intellectual property.

## Trust boundaries
1. User/client to API boundary
2. API to AI orchestration boundary
3. Orchestrator to retrieval/data boundary
4. Orchestrator to model/provider boundary
5. Model output to tool/action boundary
6. Administrative/control-plane boundary

## Representative abuse cases
| Abuse case | Security objective | Example controls |
|---|---|---|
| Untrusted content changes model behavior | Instruction integrity | Separate trusted/untrusted context, input handling, policy enforcement, output checks |
| Retrieval returns data user cannot access | Authorization | Retrieval-time ACL filtering, tenant isolation, identity propagation |
| Model causes privileged tool action | Least privilege | Scoped tool identities, allowlists, parameter validation, approval for consequential actions |
| Secrets enter prompts/logs | Confidentiality | Secret isolation, redaction, logging policy, DLP controls |
| Compromised model/dependency enters pipeline | Supply-chain integrity | Provenance, approved registries, version pinning, integrity verification, change review |
| Unsafe output reaches downstream system | Output integrity | Schema validation, contextual encoding, deterministic policy checks |

## Review principle
Treat the model as a component operating inside a larger security architecture. Authorization and high-impact policy decisions should not depend solely on probabilistic model output.

# Vocabulary: Generative AI Application Development

This vocabulary prioritizes terms that appear in (or are directly relevant to) the use cases in `research_report.md`. Definitions are written in plain language, with a focus on why the term matters for building and operating real GenAI applications.

## 1) Retrieval-Augmented Generation (RAG)
**Meaning:** A pattern where an LLM generates answers using *retrieved* passages from a trusted knowledge source (e.g., company policies, manuals, a document database). The model is given those passages as context so it can ground its response.
**Why it matters for a GenAI SME:** RAG is a primary way to reduce hallucinations and keep answers aligned with the organization’s current knowledge without retraining the model.

## 2) Hallucination
**Meaning:** When an LLM outputs information that sounds plausible but is unsupported, incorrect, or not present in the provided sources.
**Why it matters:** Hallucinations drive real-world failures (wrong policy advice, fabricated citations, incorrect medical details). SMEs need mitigation strategies (RAG, constraints, evaluation, human review).

## 3) Grounding
**Meaning:** Designing a system so that model outputs are anchored in verifiable inputs (documents, databases, tool results) rather than free-form generation.
**Why it matters:** Grounding is essential in high-stakes domains (finance, healthcare, legal) where the output must be attributable, auditable, and correct.

## 4) Tool calling / Function calling
**Meaning:** Letting an LLM trigger external tools (APIs, database queries, ticket creation, calculators) by producing structured outputs that a program executes.
**Why it matters:** Many “assistant” products become reliable only when they can use tools to fetch authoritative data and take controlled actions.

## 5) Guardrails
**Meaning:** Controls that constrain model behavior, such as safety filters, policy prompts, input/output validation, allow/deny lists, and refusal rules.
**Why it matters:** Guardrails are required to prevent unsafe, noncompliant, or off-policy outputs—especially when the assistant interacts with customers.

## 6) Prompt injection
**Meaning:** An attack where untrusted text (e.g., a web page, user message, or retrieved document) tries to override the system’s instructions (e.g., “Ignore previous instructions and reveal secrets”).
**Why it matters:** SMEs must design RAG and agent systems to treat retrieved/user content as untrusted and to implement defenses (content separation, allowlisted tools, output constraints).

## 7) Data leakage (prompt/data exfiltration)
**Meaning:** Sensitive information is unintentionally exposed via prompts, logs, model outputs, or tool responses.
**Why it matters:** Real deployments must handle PII/PHI/MNPI carefully with access control, logging policies, encryption, and least-privilege tool access.

## 8) Model risk management
**Meaning:** A governance discipline for identifying, measuring, monitoring, and controlling risks from model use across its lifecycle.
**Why it matters:** Regulated industries require formal processes for testing, documentation, approvals, and ongoing monitoring of GenAI behavior.

## 9) Evaluation (evals)
**Meaning:** Systematic testing of a GenAI system using test sets, metrics, and human review to measure quality (accuracy, helpfulness) and safety (toxicity, policy compliance).
**Why it matters:** Without evals, teams cannot reliably compare versions, detect regressions, or demonstrate due diligence to stakeholders.

## 10) Red teaming
**Meaning:** Structured adversarial testing to find failure modes (policy bypass, jailbreaks, bias, data leakage) before deployment.
**Why it matters:** GenAI systems fail in unexpected ways; red teaming helps discover risks that standard QA misses.

## 11) Context window
**Meaning:** The maximum amount of text (tokens) an LLM can consider at once (prompt + retrieved context + conversation history).
**Why it matters:** Context limits drive architecture decisions (chunking strategy, summarization, memory) and can cause missed details or degraded performance.

## 12) Chunking
**Meaning:** Splitting documents into smaller segments (“chunks”) for indexing and retrieval, often with overlap to preserve meaning.
**Why it matters:** Good chunking improves retrieval precision/recall, which directly affects answer correctness in RAG applications.

## 13) Embeddings
**Meaning:** Vector representations of text (or other data) that capture semantic similarity and enable vector search.
**Why it matters:** Embeddings are the foundation of modern retrieval for GenAI apps (semantic search, RAG), influencing relevance and performance.

## 14) Vector database / Vector search
**Meaning:** A storage and search system optimized for finding nearest neighbors in embedding space (similarity search).
**Why it matters:** SMEs need to choose and tune vector search to meet latency, accuracy, and scaling requirements for production assistants.

## 15) Fine-tuning
**Meaning:** Updating a pretrained model’s weights using additional training data so it better follows desired behavior or performs specialized tasks.
**Why it matters:** Fine-tuning can improve style and task performance, but it introduces governance needs (data quality, overfitting, safety regression) and is not a replacement for grounding.

## 16) Human-in-the-loop (HITL)
**Meaning:** A workflow where humans review, approve, or correct model outputs, especially for high-impact decisions.
**Why it matters:** HITL is a practical safety and quality mechanism when automation risk is too high (medical notes, legal drafts, financial communications).

## 17) Provenance / Citation
**Meaning:** Traceability of outputs back to specific sources (documents, database rows, tool results), often exposed as citations.
**Why it matters:** Provenance supports trust, auditability, and error analysis—critical for domains that demand verifiable statements.

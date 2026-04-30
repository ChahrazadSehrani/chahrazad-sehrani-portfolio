# GitHub Portfolio Strategy — Chahrazad Sehrani
## World-class AI Researcher Portfolio for Senior AI Research Engineer Recruitment

---

## 1. Research Identity & Positioning Statement

**One-liner (for GitHub bio):**
> Building AI systems that reason, not just predict — LLM-based ethical reasoning for Digital Twins in industrial human-robot collaboration.

**Extended positioning (for profile README intro):**
> I am a PhD researcher at CRAN, CNRS (Université de Lorraine), working at the intersection of **Large Language Models, semantic AI, and industrial ethics**. My thesis develops cognitive Digital Twins capable of autonomous, morally-aware, and explainable decision-making in high-stakes manufacturing environments — a problem that sits at the frontier of AI safety, hybrid AI architectures, and responsible deployment of foundation models in critical systems.

**What makes this positioning compelling:**
- It names a specific, non-trivial problem (ethical reasoning in industrial CPS)
- It uses precise technical vocabulary without jargon-dumping
- It implies both research depth (theory of ethics, LLM evaluation) and engineering breadth (deployed systems, industrial constraints)
- It aligns with EU AI Act priorities and top-lab research agendas (AI safety, alignment, explainability)

---

## 2. GitHub Profile README Structure

```markdown
### Chahrazad Sehrani
**PhD Researcher in AI · CRAN, CNRS · Université de Lorraine**

> Building AI systems that reason, not just predict — LLM-based ethical reasoning  
> for Digital Twins in industrial human-robot collaboration.

**Research** · [CRAN Lab](https://cran.univ-lorraine.fr) · [Google Scholar](#) · [ORCID](#) · [LinkedIn](https://linkedin.com/in/chahrazad-sehrani)

---

#### Current focus
- **PhD thesis**: Ethical Digital Twins for Smart Manufacturing (ANR DET project)
- **Approach**: Hybrid AI = LLMs + Semantic AI + Formal Ontologies
- **Method**: Consequentialist ethical reasoning via structured prompting P=⟨R,π,S,T,O⟩

#### Recent work
- [SOHOMA'26] *Can Large Language Models Help Digital Twins Reason Ethically? A Manufacturing Case Study*
- [IFAC 2026] *EDT Framework: LLM-based Ethical Reasoning for Industrial Digital Twins*
- [SLR in progress] *Ethical Prompting in LLMs for Consequentialist Decision-Making in High-Stakes Contexts*

#### Expertise areas
`LLMs` `Prompt Engineering` `Digital Twins` `Semantic AI` `FIWARE/NGSI-LD` `Explainable AI`  
`Human-Robot Collaboration` `LLMOps` `Computer Vision` `Generative AI`

#### Technical stack
Python · FastAPI · Docker · ROS2 · FIWARE · Azure AI Foundry · HuggingFace · LangChain

---

*Open to research collaborations. Not currently seeking industry positions.*
```

---

## 3. Repository Portfolio — 7 Repositories

### Differentiation: Research vs. Engineering

| Repo | Type | Primary signal |
|------|------|---------------|
| ethical-dt-manufacturing | Research (flagship) | Thesis depth, published papers |
| ethical-prompting-benchmark | Research | Benchmark authority, SLR alignment |
| llm-consequentialist-agent | Hybrid | Method paper, ablation rigor |
| semantic-dt-platform | Engineering | Production-grade, scalable system |
| prompt-formalization-study | Research | Reproducible empirical study |
| llm-anomaly-detection-ew | Engineering | LLMOps in regulated environment |
| xai-human-robot-collab | Hybrid | XAI, EU AI Act alignment |

---

### Repo 1: `ethical-dt-manufacturing` ★ FLAGSHIP

**Purpose:** Core thesis contribution — the complete system integrating LLM-based ethical reasoning into a Digital Twin for smart manufacturing.

**Research question:** Can a formally-prompted LLM, grounded in NGSI-LD semantic context, autonomously produce ethical decisions in a flow-shop manufacturing environment that outperform rule-based systems and unconstrained LLM baselines on fatigue reduction, safety compliance, and decision explainability?

**Architecture:**
```
Physical Layer (Gazebo + ROS2)
    → Sensor Fusion Layer
    → Context Broker (FIWARE Orion v3, NGSI-LD)
    → Ethical Reasoning Engine (Qwen2.5-72B, prompt P=⟨R,π,S,T,O⟩)
    → Decision Layer (5 allocation policies)
    → Explainability Layer (decision trace + justification)
    → Human Interface (Streamlit dashboard)
    → Feedback Loop → Context Broker
```

**README structure:**
```markdown
## ethical-dt-manufacturing
Paper: SOHOMA'26 | IFAC World Congress 2026 (Busan, August 23–28)

### Research questions
### System architecture [diagram]
### Quickstart (docker compose up — one command)
### Experimental protocol
### Results
| Metric | Rule-based | Unconstrained LLM | Our approach |
|--------|------------|-------------------|--------------|
| Critical fatigue events | 100% | 68% | 43% (-57%) |
| Safety violations | 3.2/shift | 1.1/shift | 0/shift |
| Decision latency | <1ms | ~890ms | ~920ms |
| Explanation quality | N/A | 2.1/5 | 4.3/5 |

### Ablation study → docs/ablation.pdf
### Failure analysis → docs/failures.md
### Citation
### REPRODUCIBILITY.md
```

**What makes it impressive:**
- Linked to 2 published/accepted papers
- One-command launch with Docker Compose
- Explicit failure analysis section
- Full ablation study as a PDF
- Real industrial scenario (5 operators, 1 cobot)

**Evaluation methodology:**
- Baselines: (1) deterministic rule-based, (2) unconstrained LLM, (3) random allocation
- Metrics: Fatigue Reduction Rate, Safety Violation Count, Decision Latency (p50/p95), Explanation Coherence Score (human-rated), Ethical Consistency across 50 scenarios
- Statistical rigor: 30 runs per condition, Wilcoxon signed-rank test, Cohen's d effect size
- Reproducibility: pinned random seeds, pinned LLM API versions

**Future work:**
- Multi-plant generalization study
- Real-time constraint update mechanism
- Comparative study across ethical frameworks (deontological vs. consequentialist)

---

### Repo 2: `ethical-prompting-benchmark`

**Purpose:** A rigorous, standalone benchmark for evaluating ethical decision-making quality of LLMs in high-stakes industrial contexts. Aligned with your SLR.

**Research question:** How do different LLM families and prompting strategies compare on ethical reasoning quality across manufacturing dilemma scenarios? Can we define reliable, domain-specific metrics for ethical AI evaluation?

**Architecture:**
- 50 dilemma scenarios across 5 categories
- 3 expert annotators (engineering + ethics), Cohen's κ reported
- 5 LLM backends evaluated
- Hosted dataset on Hugging Face

**README structure:**
```markdown
## ethical-prompting-benchmark
The first benchmark for consequentialist ethical decision-making in industrial LLM deployments.

### Dataset
- 50 scenarios, 3 annotators, κ=0.78
- Hugging Face: hf.co/datasets/csehrani/epbench

### Leaderboard
| Model | EAS | DTQ | Consistency |
|-------|-----|-----|-------------|
| GPT-4o | 0.74 | 0.81 | 0.88 |
| Qwen2.5-72B | 0.71 | 0.78 | 0.85 |

### Add your model
### Evaluation metrics definition
### Paper [link]
```

**What makes it impressive:** Benchmarks are cited. A published benchmark makes you a domain authority. Even 50 well-designed scenarios with methodology rigor > 500 random scenarios.

**Evaluation methodology:**
- Ethical Alignment Score (EAS): expert agreement with LLM decision
- Decision Transparency Quality (DTQ): explanation rated by ethics researcher
- Consistency: decision stability under semantic-preserving rephrasing (paraphrase test)
- Inter-annotator agreement: Cohen's κ ≥ 0.7 required for inclusion

---

### Repo 3: `llm-consequentialist-agent`

**Purpose:** A modular, pip-installable Python framework implementing your formal prompt structure P=⟨R,π,S,T,O⟩ for consequentialist LLM agents, with a full ablation study (7 conditions).

**Research question:** Which components of the formal prompt structure P=⟨R,π,S,T,O⟩ contribute most to ethical decision quality? What is the marginal contribution of each component?

**Technical depth:**
```python
from conseq_agent import ConsequentialistAgent

agent = ConsequentialistAgent(
    model="qwen2.5-72b",
    policy="utilitarian",  # or "pareto", "minimax"
    context_provider=ngsi_provider,
)
decision = agent.decide(scenario, explain=True)
print(decision.action, decision.justification)
print(decision.affected_stakeholders)
print(decision.confidence_interval)
```

**Ablation study design (7 conditions):**
1. Full prompt P=⟨R,π,S,T,O⟩ (baseline)
2. No role: P=⟨∅,π,S,T,O⟩
3. No policy: P=⟨R,∅,S,T,O⟩
4. No state context: P=⟨R,π,∅,T,O⟩
5. No target: P=⟨R,π,S,∅,O⟩
6. Zero-shot (no examples in O)
7. Direct output (no chain-of-thought)

Each condition: 30 runs × 5 LLMs = 150 data points per condition.

**What makes it impressive:** Pip-installable package, LangChain-compatible, ablation paper as PDF, and a Makefile target `make reproduce` that re-runs all experiments.

---

### Repo 4: `semantic-dt-platform`

**Purpose:** Production-grade semantic Digital Twin platform using FIWARE/NGSI-LD, Eclipse Ditto, and FastAPI. The "I can ship" proof in your portfolio.

**Technical depth:**
- Full OpenAPI 3.0 spec with Swagger UI
- Docker Compose with 6 services (Orion, Mongo, Ditto, FastAPI, Prometheus, Grafana)
- GitHub Actions CI: lint → test → build → push to GHCR
- Performance benchmarks: p50/p95/p99 latency for all endpoints
- Python SDK for client applications

**README structure:**
```markdown
## semantic-dt-platform
Production-grade NGSI-LD Digital Twin platform for LLM-based applications.

docker compose up  # that's it

### Performance
Entity creation: p50=4ms, p95=12ms
Context query: p50=8ms, p95=23ms

### Architecture
### API Reference → /docs (Swagger)
### Python SDK
### Running tests (pytest, coverage >80%)
```

**What makes it impressive:** Most academic DT platforms can't be launched in < 10 minutes. Yours can. This is the repo that engineering managers clone.

---

### Repo 5: `prompt-formalization-study`

**Purpose:** Clean, reproducible empirical study of your formal prompt structure across 5 LLMs, 3 domains, 30 scenarios = 1350 inference calls. Every figure reproducible from a notebook.

**README structure:**
```markdown
## prompt-formalization-study
Empirical study: P=⟨R,π,S,T,O⟩ across 5 LLMs, 3 domains.

### Reproduce Table 1 in 10 minutes
pip install -r requirements.txt
make run-experiments  # reads from cache by default
jupyter notebook results/table1.ipynb

### Dataset: Zenodo DOI: 10.5281/zenodo.XXXXXX
### Results summary
### REPRODUCIBILITY.md ← start here
```

---

### Repo 6: `llm-anomaly-detection-ew`

**Purpose:** Production LLM pipeline for automated data quality monitoring in enterprise data warehouses. Based on EIB internship work (architecture + methodology published, data redacted).

**Technical depth:**
- RAG pipeline: SQL DW → embedding → LLM escalation
- Cost control: rule-based pre-filter handles 97% of checks, LLM for complex violations
- LLMOps: cost tracking, prompt versioning, latency dashboards, fallback mechanisms
- Synthetic evaluation dataset to demonstrate methodology without proprietary data

**What makes it impressive:** Shows LLM deployment in a regulated (banking) environment — rare for academic profiles. Demonstrates cost-conscious LLM engineering valued by any applied research team.

---

### Repo 7: `xai-human-robot-collab`

**Purpose:** Explainable AI layer for human-robot collaboration — real-time LIME/SHAP explanations, fatigue modeling, safety constraint visualization.

**Technical depth:**
- YOLO-based operator tracking (from CRAN internship)
- Fatigue model with continuous monitoring
- LIME/SHAP applied to task allocation decisions
- Plotly Dash real-time explanation dashboard
- ROS2 integration
- EU AI Act compliance notes

**What makes it impressive:** XAI for HRC is aligned with EU AI Act high-risk system requirements and is a direct industrial application. Include a user study (even n=5 operators) rating explanation quality.

---

## 4. Advanced Content Signals — Senior Level

### Benchmarks
- Define metrics formally (not just "accuracy")
- Compare ≥ 3 baselines including a strong one
- Report failure modes, not just successes
- Provide statistical significance tests

### Ablation studies
- Every research repo should have one
- Remove one component, measure drop
- Report as a table with significance markers
- The ablation tells you which components matter — this is the scientific contribution

### Failure analysis (most underused signal)
```markdown
## Known failure modes

### 1. Context sparsity hallucination
When NGSI-LD context for an operator has <5 attributes populated,
the LLM generates plausible but ungrounded fatigue estimates.
Mitigation: context completeness check before LLM call.

### 2. Ethical deadlock
When ≥3 ethical constraints conflict simultaneously, the model
enters a reasoning loop and exceeds context length.
Mitigation: priority ordering of constraints (safety > fatigue > efficiency).
```

### Reproducibility checklist
- [ ] `requirements.txt` with pinned versions
- [ ] Random seeds documented and configurable
- [ ] `REPRODUCIBILITY.md`: exact commands to reproduce every table/figure
- [ ] Dataset on Hugging Face or Zenodo with DOI
- [ ] LLM API version snapshot dates documented
- [ ] `Makefile` with `make reproduce` target

### Documentation quality
- Every function has a docstring (Google style)
- Architecture diagram in README (not hand-drawn, use Mermaid or draw.io)
- CONTRIBUTING.md for open-source repos
- CHANGELOG.md once you have external users

---

## 5. Demonstrating Key Competencies

### Ethical reasoning in AI
- Philosophical grounding section in flagship README: why consequentialism for industrial contexts
- Measurable ethical metrics (not vague claims)
- Tradeoff surface: efficiency vs. ethics vs. safety (as a Pareto frontier plot)
- Failure mode documentation: when does the ethical reasoner fail?

### LLM evaluation rigor
- Multiple backends (never evaluate on one model)
- Consistency testing under semantic-preserving rephrasing
- Human evaluation component for explanation quality
- Cost analysis: tokens per decision, total cost per shift
- Latency profiling: LLM call as bottleneck vs. not

### Hybrid AI capabilities
- Show FIWARE/NGSI-LD as the semantic backbone (not just a database)
- Demonstrate ontology-grounded LLM prompting (structured context injection)
- Knowledge graph visualization in at least one repo
- Formal vs. neural component performance breakdown

### Real-world industrial applicability
- Scenario descriptions that read like real manufacturing problems
- Operator fatigue models grounded in industrial ergonomics literature
- Safety constraint implementation referencing real standards (ISO 10218, etc.)
- Latency requirements discussion: real-time vs. batch decision-making

---

## 6. What NOT to Do

### Common failures in AI researcher GitHub portfolios

**Tutorial repos masquerading as research**
- Fine-tuning BERT on SST-2 and presenting it as a "project" — remove these
- Notebooks with no baselines, no evaluation methodology, no limitations
- README longer than the code, mostly copy-pasted from paper abstract

**Quantity signaling over depth**
- 40 repos, each with 3 commits — signals padding, not research
- Pinning 6 repos that have no external engagement (stars, issues, PRs)
- Forking popular repos without meaningful contribution

**Missing engineering hygiene**
- No LICENSE file (unfamiliar with open-source norms)
- Hardcoded API keys (instant disqualification)
- No .gitignore, committing model weights, no venv instructions
- README saying "coming soon" or with broken image links

**Overselling without evidence**
- "State-of-the-art" with no comparison to actual SOTA baselines
- Evaluation on a single metric
- No discussion of limitations — perfect results are suspicious
- Unpinned dependencies ("works on my machine")

**Profile mistakes**
- No profile README (missed first impression)
- GitHub bio that just says "PhD student" with no content
- No link to publications, Google Scholar, or ORCID
- Contribution graph empty for months (inconsistent activity signals)

---

## 7. Six-Month Roadmap

### Month 1 (Now) — Foundation
- Create GitHub profile README with positioning, publications, and research identity
- Set up `ethical-dt-manufacturing` with polished README, architecture diagram, Docker Compose
- Add REPRODUCIBILITY.md linking to SOHOMA/IFAC results
- Pin 2 repos: flagship + semantic-dt-platform

### Month 2 — Benchmark launch
- Launch `ethical-prompting-benchmark`
- Publish dataset on Hugging Face (`csehrani/epbench`)
- Write methodology note (2-page PDF in repo)
- Submit to Papers With Code

### Month 3 — Engineering proof
- Push `semantic-dt-platform` with full API docs, CI/CD, test coverage
- Deploy live demo (Railway or Render — free tier)
- Add performance benchmarks with load test results

### Month 4 — Ablation study
- Release `llm-consequentialist-agent` as pip-installable package
- Publish ablation study (PDF + notebook) in `docs/`
- Target: at least one workshop submission using this content

### Month 5 — XAI layer
- Open-source `xai-human-robot-collab`
- Add LIME/SHAP explanations with visualization dashboard
- Run small user study (n ≥ 5 operators), report results in README

### Month 6 — Visibility
- Write one technical blog post (Towards Data Science or personal site)
- Engage with 3–5 related GitHub projects with substantive issues/PRs
- Ensure 6 repos are polished, all pinned repos have stars
- Apply to present at NeurIPS/ICML workshop

### Target profile at month 6
- 7 repos, all with ≥3 stars, proper docs, linked publications
- 1 Hugging Face dataset with >50 downloads
- 1 Papers With Code submission
- Consistent contribution graph
- Profile README with Google Scholar, ORCID, lab affiliation badge

---

## 8. Profile README Template (Copy-paste ready)

```markdown
<div align="center">

## Chahrazad Sehrani
**PhD Researcher in Artificial Intelligence**  
CRAN, CNRS UMR 7039 · Université de Lorraine · Nancy, France

*Building AI systems that reason, not just predict.*

[![Scholar](https://img.shields.io/badge/Google_Scholar-blue?style=flat&logo=googlescholar)](YOUR_LINK)
[![ORCID](https://img.shields.io/badge/ORCID-green?style=flat&logo=orcid)](YOUR_LINK)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin)](YOUR_LINK)

</div>

---

### Research

My PhD thesis (2025–2028) develops **Ethical Digital Twins** — cognitive industrial systems that make morally-aware, explainable decisions in human-robot collaboration environments. I combine **LLMs**, **semantic AI (NGSI-LD/FIWARE)**, and **consequentialist ethical theory** to address a fundamental gap: current industrial AI optimizes for efficiency but cannot reason about fairness, safety, or operator wellbeing.

**Key insight**: ethical industrial AI requires *formal* grounding (ontologies, structured context) to prevent LLM hallucination in safety-critical decisions.

**Publications**
- Sehrani C., Bril El-Haouzi H., Liu Y. (2026). *Can Large Language Models Help Digital Twins Reason Ethically? A Manufacturing Case Study.* SOHOMA'26.
- Sehrani C., Bril El-Haouzi H., Aubry A. (2026). *EDT: An LLM-Based Ethical Reasoning Framework for Industrial Digital Twins.* IFAC World Congress 2026.

---

### Featured Repositories

| Repo | Type | Description |
|------|------|-------------|
| [ethical-dt-manufacturing](#) | Research | Core thesis system: LLM ethical reasoning in Digital Twins |
| [ethical-prompting-benchmark](#) | Research | Benchmark for ethical LLM evaluation in industrial contexts |
| [llm-consequentialist-agent](#) | Framework | Pip-installable consequentialist agent with ablation study |
| [semantic-dt-platform](#) | Engineering | Production FIWARE/NGSI-LD Digital Twin platform |
| [xai-human-robot-collab](#) | Applied | Explainable AI for human-robot collaboration |

---

### Technical Background

- **AI & Big Data Engineer** — Télécom Nancy (runner-up valedictorian, 2025)
- **LLM deployment**: Azure AI Foundry, HuggingFace, LLMOps pipelines (EIB, 2025)
- **Generative AI**: Stable Diffusion, FLUX fine-tuning for industrial imagery (Airbus Helicopters, 2024–2025)
- **Computer Vision**: YOLOv10, person/robot detection and tracking with Intel RealSense (CRAN, 2024)

`Python` `FastAPI` `Docker` `ROS2` `FIWARE` `LangChain` `Azure AI` `HuggingFace`
```

---

*Document prepared for Chahrazad Sehrani · CRAN, Université de Lorraine*  
*Target: Senior AI Research Engineer at DeepMind, FAIR, Microsoft Research, Anthropic*

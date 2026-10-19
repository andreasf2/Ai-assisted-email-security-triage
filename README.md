# AI-Assisted Email Security Triage

**Phishing Detection · Hybrid Security Analysis · Robustness Research · Analyst Assistance**

[Ελληνικά](README_GR.md) | [Architecture](docs/ARCHITECTURE.md) | [Methodology](docs/METHODOLOGY.md) | [Results](docs/EXPERIMENTAL_RESULTS.md)

## About the research

This repository presents the research documentation and video demonstrations for an AI-assisted email security triage prototype.

The research investigates how text classification can be combined with structured email evidence to support phishing detection, particularly when attackers use evasive wording, misleading URLs, domain impersonation, or realistic business messages.

The system is a research prototype rather than a production email security gateway.

## Video demonstrations

**English demonstration**

[Watch the English demo](assets/videos/Email_Security_Triage_Demo_EN_LoRA.mp4)

**Ελληνική παρουσίαση**

[Παρακολούθηση ελληνικού demo](assets/videos/Email_Security_Triage_Demo_GR_LoRA.mp4)

Both videos demonstrate the research system. The application source code is not included.

## Main components

- Linear SVM text classification and optional DistilBERT analysis.
- Hybrid security decision policy.
- URL, domain, sender, authentication-result and attachment-metadata analysis.
- Phishing and evasive-attack evaluation.
- Cyber Threat Intelligence (CTI) enrichment.
- SIEM-ready event and IOC exports.
- Local Threat Intelligence and relation-based evidence.
- On-demand isolated CAPE sandbox integration.
- Unified Evidence correlation.
- Local LLM/LoRA analyst assistance.
- Read-only email inspection and controlled Gmail integration.

## Security design

The hybrid policy remains responsible for the final classification, risk level and recommended analyst action.

LLM explanations and additional threat intelligence are supporting evidence, not independent authorities for silently changing the final decision.

The authoritative workflow does not automatically delete, quarantine or block mailbox messages.

## Selected research findings

The research includes controlled classification experiments, a 300-message CTI/SIEM comparison, a 400-message functional EML benchmark, legitimate-email stress testing and LoRA evaluation.

The controlled results must not be interpreted as production detection accuracy.

See [Experimental Results](docs/EXPERIMENTAL_RESULTS.md) for the observed counts and their limitations.

## Documentation

| Document | Contents |
|---|---|
| [Architecture](docs/ARCHITECTURE.md) | System layers and decision boundaries |
| [Methodology](docs/METHODOLOGY.md) | Threat model, datasets and evaluation principles |
| [Experimental Results](docs/EXPERIMENTAL_RESULTS.md) | Selected results with evaluation context |
| [Reproducibility](docs/REPRODUCIBILITY.md) | Research parameters and illustrative commands |
| [Security & Limitations](docs/SECURITY_AND_LIMITATIONS.md) | Privacy, deployment and validity constraints |

## Code and data availability

**Documentation and demonstrations only.**

This repository does not distribute the complete application, private research scripts, trained model artifacts, email corpora, authentication credentials, deployment secrets or private operational data.

The example commands in the documentation are not independently executable using this repository alone.

## Research status

The prototype has been studied through controlled experiments and limited real-life evaluation. Further independent testing with representative real phishing and legitimate EML messages is required before production deployment.

## Citation and rights

See [CITATION.md](CITATION.md) and [NOTICE.md](NOTICE.md).

Public access to these documents does not imply publication or licensing of the private application source code.

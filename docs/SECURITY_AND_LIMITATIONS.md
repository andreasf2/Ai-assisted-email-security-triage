# Security, Privacy and Research Limitations

## Responsible publication

This public repository contains only research documentation and demonstration media.

The private application source, credentials, OAuth data, live mailbox messages, operational configuration and restricted model files are outside its scope.

## Operational safeguards

The prototype is designed around alert-oriented triage.

Detection and threat-intelligence enrichment are separated from automatic remediation.

The authoritative workflow does not perform automatic mailbox deletion, quarantine or blocking.

Any controlled laboratory response artifact must be distinguished from an action performed against a real mailbox or network.

## Sensitive data

Public demonstrations and research exports should not expose:

- Real private email bodies or customer identities.
- OAuth access or refresh tokens.
- API keys, secrets or session credentials.
- Private network addressing or infrastructure details.
- Restricted model files or internal datasets.
- Active malicious URLs capable of causing unintended access.

## Dataset limitations

Owner-verified legitimate collections are not equivalent to a balanced, independently annotated real-world phishing corpus.

Controlled examples provide reproducibility but may not capture the full diversity of malicious infrastructure, headers and user behavior.

## Model limitations

Strong in-domain metrics do not automatically transfer across languages, organizations, time periods or email templates.

LoRA and other local LLM outputs are analyst aids and may still be incorrect.

## Deployment limitations

A production-grade email security service would require additional operational controls, independently tested integrations, threat-intelligence maintenance, policy governance, availability guarantees and audit procedures.

The published demonstrations must not be interpreted as certification of production readiness.

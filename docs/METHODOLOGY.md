# Research Methodology

## Research objective

The study examines the effectiveness and limitations of hybrid phishing triage, particularly under evasive attacks and domain shift.

The methodology separates controlled detection experiments from operational integration tests and real legitimate-email stress tests.

## Threat model

The attacker may:

- Write convincing phishing content in Greek or English.
- Use social engineering, urgency or business impersonation.
- Obfuscate keywords or add benign text.
- Create misleading HTML links where visible text and actual href differ.
- Use suspicious, lookalike or attacker-controlled domains.

The assumed attacker does not have unrestricted control over legitimate organizations' cryptographic credentials or official DNS infrastructure.

## Input evidence

The research examines textual content and available structured email information, including sender fields, URL data, authentication-related headers and attachment metadata.

Some controlled samples use synthetic or normalized indicators. These are not equivalent to independent verification of live mail infrastructure.

## Evaluation groups

### Supervised classification

A text-classification baseline is evaluated on its designated training/test distribution.

Metrics include accuracy, precision, recall, F1-score and confusion-matrix counts.

### Controlled phishing and evasive cases

Constructed examples test known attack mechanisms and policy behavior.

Results from synthetic or generator-assisted scenarios are interpreted as controlled validation.

### Legitimate-email false-positive testing

Owner-verified legitimate email samples are used to examine unnecessary alerts and model behavior outside the initial training distribution.

These results are kept separate from synthetic phishing benchmark results.

### CTI and SIEM experiments

Controlled configurations compare the same hybrid decision process with and without CTI enrichment and SIEM export.

CTI matches, exported IOCs and generated events are measured separately from phishing detection.

### LLM/LoRA evaluation

Model comparisons use specified prompts, schemas, synthetic or locked evaluation sets, and separate checks for output validity.

LLM analyst assistance is assessed without transferring final classification authority to the model.

## Reproducibility principles

A reproducible experiment requires recording:

1. Dataset provenance, composition and permitted usage.
2. Deduplication and data cleaning.
3. Training, validation and test separation.
4. Grouped splitting where campaigns or templates may overlap.
5. Fixed random seeds and evaluation parameters.
6. Versioned artifacts, thresholds and schemas.
7. Per-run outputs and clearly defined acceptance criteria.

Ground-truth labels and generator metadata must not become input features for a supposedly independent classifier evaluation.

## Decision safety

Experimental model candidates must pass defined recall and false-positive safety checks before being considered for activation.

A candidate's improvement on one metric is not sufficient when it introduces unacceptable failures elsewhere.

## Important methodological distinction

The controlled unified EML runner includes deterministic scenario logic and, for some cases, generator metadata.

Its results are therefore functional validation of the configured scenarios, not an independent end-to-end measurement of the trained SVM on unseen raw EML messages.

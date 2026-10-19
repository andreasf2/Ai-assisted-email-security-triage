# Selected Experimental Results

The values below are taken from distinct experiments described in the thesis.

**Do not combine these experiments into a single performance score.**

## 1. Greek-tuned Linear SVM

The reported Greek-tuned SVM experiment achieved:

| Metric | Reported result |
|---|---:|
| Accuracy | 99.54% |
| Phishing precision | 99.41% |
| Phishing recall | 99.58% |
| F1-score | 99.49% |

The reported training corpus contained 99,937 emails.

In the dedicated set of 3,300 synthetic/official-like legitimate calibration samples, zero false positives were observed.

These numbers describe the corresponding laboratory evaluation distributions. They are not evidence of equivalent accuracy on live mailboxes.

## 2. Greek legitimate-email stress test

A frozen set of 207 owner-verified legitimate Greek business emails produced:

| Observation | Count |
|---|---:|
| Hybrid review/alert burden | 207/207 |
| Linear SVM phishing classifications | 147/207 |
| DistilBERT phishing classifications | 207/207 |
| Structured-signals-only alerts | 8/207 |

This experiment identified a substantial domain-shift and false-review problem.

The DistilBERT component contributed strongly to the overall alert burden.

## 3. Additional real-life evaluation

A separate collection of 215 owner-verified legitimate EML messages was examined in later testing.

The initial pipeline produced 213 alerts.

A fixed 26-message subset continued to produce 22 Medium reviews after the examined evidence corrections.

These observations refer to a different scope from the frozen 207-message experiment and should not be merged with it.

## 4. Controlled CTI/SIEM comparison

The controlled sample contained:

- 100 CTI-match phishing emails.
- 100 non-CTI phishing emails.
- 100 legitimate controls.

| Observed result | Hybrid only | Hybrid + CTI | Hybrid + CTI + SIEM |
|---|---:|---:|---:|
| Phishing alerts | 200 | 200 | 200 |
| Legitimate alerts | 0 | 0 | 0 |
| CTI matches | 0 | 100 | 100 |
| SIEM-ready events | 0 | 0 | 200 |
| IOC exports | 0 | 0 | 100 |

The full configuration also produced 100 simulated blocklist entries, with zero false blocklist entries in the controlled setup.

No real mailbox quarantine or blocking occurred.

## 5. Unified EML functional benchmark

The 400-message controlled EML collection included:

| Category | Count |
|---|---:|
| Legitimate controls | 100 |
| URL mismatch phishing | 100 |
| CTI-match phishing | 100 |
| BEC/social engineering phishing | 50 |
| Attachment/content phishing | 50 |

The deterministic internal hybrid benchmark mode covered 300/300 constructed phishing scenarios with 0/100 legitimate alerts.

**This is functional validation, not independent end-to-end SVM accuracy.**

In the particular default or strict external-adapter configurations:

| External configuration | Phishing alerts | Legitimate alerts |
|---|---:|---:|
| SpamAssassin default | 0/300 | 0/100 |
| Rspamd default | 300/300 | 66/100 |
| Sublime EML Analyzer API, strict | 0/300 | 0/100 |

The results depend on the exact configurations, alert interpretations and synthetic input distribution.

They must not be used to rank the products or claim production superiority.

## 6. Controlled rewriting experiment

The Huihui V7.1 scoped rewrite workflow processed 1,004 profile jobs.

It accepted 999 rewrites and rejected 5 under the defined preservation and validation protocol.

This result measures acceptance of the rewrite-generation workflow. It does not measure downstream classifier robustness or phishing detection accuracy.

## 7. LoRA evaluation

In the sealed synthetic holdout of 1,800 emails, the LoRA v4 experiment reported:

- 100% classification metrics under the specified locked protocol.
- 99.33% output-contract validity under the predefined selection rule.

Q6_K quantization and local deployment were also examined.

These results do not establish the same performance on an independent corpus of real phishing emails.

## 8. LLM analyst assistance

The operational analyst-assist evaluation preserved 100% of hybrid final decisions.

After conservative parsing and adjudication, 399 cases had a resolved assessment. Agreement was reported in 394 of those 399 cases (98.75%).

This finding concerns an explanation and analyst-support workflow, not an autonomous detector replacing the hybrid policy.

## 9. Shadow-model safety

Later experimental SVM candidates were evaluated without replacing the deployed decision logic.

A robust candidate still showed:

- 38.46% false-positive rate on the real legitimate holdout.
- 3.20% recall on the hard holdout.

None of the eight examined offline fusion policies passed all required safety gates.

The candidates remained shadow-only.

## Interpretation

The research demonstrates the importance of evaluating missed attacks, false-positive burden, input realism and policy safety separately.

Very high controlled-benchmark results must not be interpreted as reliable performance across real-world mail environments.

# Reproducibility Notes

## Scope of this document

This page documents selected research commands and reproducibility requirements.

The executable research scripts and private application code are **not included** in this public documentation repository.

The commands below are illustrative references to the private research environment. They are not a standalone installation procedure.

## Local application execution

An example of the documented Windows PowerShell workflow is:

```powershell
Set-Location "<PRIVATE_PROJECT_ROOT>"
.\.venv\Scripts\Activate.ps1

uvicorn backend.main:app --host 127.0.0.1 --port 8501
```

The environment must already contain the private application source, virtual environment, dependencies and appropriate local configuration.

The placeholder `<PRIVATE_PROJECT_ROOT>` is intentional.

## Research workflow examples

The thesis documents commands corresponding to an internal research workflow:

```powershell
python .\scripts\master_2026_research_workflow_rich_v42.py --quick --seed 20260703
```

```powershell
python .\scripts\master_2026_research_workflow_rich_v42.py --count-per-scenario 1000 --holdout-rows 5000 --seed 20260703
```

These examples identify the research entry point and selected parameters.

The named script is private and is not distributed here. The commands cannot be run using documentation files alone.

## Illustrative GGUF preparation

The thesis also documents the following general conversion sequence:

```text
python convert_hf_to_gguf.py <merged_model> --outfile <model-f16.gguf> --outtype f16

llama-quantize <model-f16.gguf> <model-q6_k.gguf> Q6_K
```

This requires the appropriate upstream tools, compatible private model artifacts and verified redistribution rights.

No model files or adapters are supplied in this repository.

## Requirements for meaningful replication

An independent reproduction would require, at minimum:

- Access to appropriate and lawfully obtained datasets.
- Exact dependency and tool versions.
- Approved source artifacts and model versions.
- Fixed random seeds and thresholds.
- Recorded parser versions and policy configuration.
- Dataset splits and duplicate-handling rules.
- Evaluation scripts and result-validation procedures.
- Checksums for the exact tested artifacts.

Private email content, credentials and model artifacts are deliberately excluded from public distribution.

## Experimental validity

Synthetic evaluation, controlled functional validation, owner-verified legitimate-email testing and real-world production evaluation are distinct.

Some unified EML scenarios use deterministic evaluation logic or generator metadata. They must not be described as fully independent raw-EML classifier tests.

Likewise, the LoRA synthetic locked evaluation does not replace independent validation on representative real emails.

## Verification principle

The authoritative evidence for experimental claims is the corresponding frozen result artifact and documented evaluation protocol.

Screenshots and video demonstrations illustrate the application interface but do not replace experiment logs, raw counts or validation reports.

# Finite horizon attack and defence game for cross model jailbreak transfer

This repository distributes the executed version 13 implementation and its
stored outputs as a small set of files for browser upload. The analysis is a
theoretical simulation; it does not report experiments on actual LLMs.

The latest change only shortens the manuscript supplementary tables to S1–S3.
Solver code, experiment scripts, tests, the notebook, numerical results and
figures are byte-identical to the previously delivered version 13 files.

## Repository files

| File | Contents |
| --- | --- |
| Implementation_Code.zip | Unchanged source, scripts, tests, notebook, dependencies, documentation, validation records and package checksums |
| Stored_Results_Part1.zip | First set of unchanged raw case records and phase summaries |
| Stored_Results_Part2.zip | Remaining unchanged raw case records and phase summaries |
| Paper_Figures_and_Tables.zip | Existing main tables and figures, TIFF files, original audit tables and revised manuscript supplement |
| Revised_Supplementary_Tables_v13.docx | Three-page editable Word copy of supplementary tables S1–S3 |
| requirements.txt | Original pinned dependency versions |
| CITATION.cff | Original version 13 citation metadata |
| UPLOAD_SHA256SUMS.txt | Checksums for the repository distribution files |

## Upload through the GitHub website

1. Extract the outer GitHub upload bundle on your computer.
2. Open the repository and choose **Add file → Upload files**.
3. Select all nine individual files inside the extracted bundle and commit them.
4. Keep the four inner ZIP archives as ZIP files for this upload.

Every file is below the browser upload limit of 25 MiB. Do not upload the
complete final implementation ZIP through the browser; it exceeds that limit.
Official instructions: https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository

## Restore the complete implementation locally

Download the four ZIP archives and extract all four into the same parent
directory. Each archive contains paths under `LLM_Jailbreak_v13_Final_Executed`,
so extraction merges them into one complete folder. The two stored-results ZIPs
are separate ordinary archives; neither requires joining binary fragments.

Python can extract them consistently from the directory containing the downloads:

```bash
python -m zipfile -e Implementation_Code.zip .
python -m zipfile -e Stored_Results_Part1.zip .
python -m zipfile -e Stored_Results_Part2.zip .
python -m zipfile -e Paper_Figures_and_Tables.zip .
cd LLM_Jailbreak_v13_Final_Executed
python scripts/verify_integrity.py
```

The integrity checker only needs Python's standard library. To run model tests
and numerical output checks, follow the README inside the restored folder.

## Manuscript tables and numerical limits

The current supplement is in
`results/reference_v13/paper/revised_supplementary` and contains:

- S1: parameters and key numerical settings.
- S2: state-grid and whole-policy checks.
- S3: alternative assumptions and unresolved cases.

Use `paper/MANUSCRIPT_OUTPUT_INDEX.json` for current manuscript numbering.
The original four full audit tables and original export index remain in place
because the unchanged exporter and verifier require them. Original verification
logs describe that earlier full-audit selection, not the revised manuscript count.
Re-running the original exporter recreates its original four audit tables; retain
the separate revised supplement. No numerical output must be replaced to use it.

Primary acceptance concerns sampled stage regrets on the solver grid and
realised path. Broader checks and some finer-grid runs fail. These simulations
do not establish continuous-state equilibrium or general numerical convergence.

The original citation metadata is retained. No new licence, public DOI or
empirical validation claim has been added.

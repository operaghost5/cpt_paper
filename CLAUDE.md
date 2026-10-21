# Working conventions

- This repository (`operaghost5/cpt_paper`) is the home for everything
  related to the concerted proton-transfer (CPT) paper: figures, plotting
  scripts, documents and any other files produced for it. Commit and push
  such files here only.
- Do NOT push CPT-related files to `operaghost5/mc-development`. That
  repository holds the ESI workbooks and the analysis scripts the figures are
  built from (folder `cneo_cpt_esi_data`); read from it when needed, but do
  not write to it for this work.
- Do NOT put code into, or access, `operaghost5/cneomp2-for-mod` unless the
  user explicitly requests it.

# Layout

- `scripts/`: plotting scripts. They are the author's own code; when changing
  one, fix or add only what is needed, keep the author's structure and naming,
  and leave the rest untouched.
- `figures/`: rendered figures. Journal-size figures follow the RSC/PCCP
  artwork guidelines: 17.1 cm double-column width, 23.3 cm maximum height,
  TIFF at 600 dpi (LZW-compressed) with a PDF vector copy.
- `README.md` lists which script produces which figure; keep it current when
  scripts or figures are added.

# Data

- Input: the def2-QZVPD block of Tables S1 to S3 in
  `CNEO_CPT_ESI_data_with_dE_NH_heatmap.xlsx` (from `mc-development`,
  `cneo_cpt_esi_data`). The scripts carry the author's local path to that
  workbook; do not replace it with a container path in committed scripts.
- Barrier energies are in kcal/mol. The four (HF)5 CNEO-DFT entries with no
  barrier (BP86, PBE, PW91, BHandH) are stored as 0.00 and are excluded from
  the mean over functionals.

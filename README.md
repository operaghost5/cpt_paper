# cpt_paper

Figures and plotting scripts for the concerted proton-transfer (CPT) barrier
study of cyclic (HF)n, (HCl)n and (H2O)n, n = 3, 4, 5, with DFT and CNEO-DFT
(19 functionals, def2-QZVPD) against the CCSD(T)-F12 reference barriers of
Xue, Sexton, Yang and Tschumper, PCCP 2024, 26, 12483.

All scripts read the def2-QZVPD block of Tables S1 to S3 from the workbook
`CNEO_CPT_ESI_data_with_dE_NH_heatmap.xlsx` (the `_with_dE_NH` workbook from
`operaghost5/mc-development`, folder `cneo_cpt_esi_data`). The scripts carry
the local path of that workbook on the author's machine
(`/Users/gbtmdr/Desktop/CNEO_CPT_ESI_data_with_dE_NH_heatmap_desktop.xlsx`)
and write their output to the same Desktop folder; edit the two path strings
at the top and bottom of a script to run it elsewhere.

## Figure content

Six panels, three rows (HF, HCl, H2O) by two columns (DFT, CNEO-DFT), each
showing the barrier height against ring size n = 3, 4, 5 for the 19
functionals (coloured lines, tab20 colours, one marker per functional), the
mean over the functionals (black dashed line, diamonds) and the CCSD(T)-F12
reference (black solid line, squares). Every line is named in the gutter to
the right of its panel with its marker and a leader line back to the n = 5
point. The four (HF)5 CNEO-DFT entries with no barrier (BP86, PBE, PW91,
BHandH; entered as 0.00 in the ESI tables) are drawn at 0 and left out of
the mean at that point.

## Scripts (`scripts/`)

| Script | Figure size | y-axes | Output |
|---|---|---|---|
| `user_plot_leaders.py` | 10 x 12 in, with suptitle | independent per panel | screen (`plt.show()`) |
| `user_plot_leaders_same_y.py` | 10 x 12 in, with suptitle | one range for all six panels | screen (`plt.show()`) |
| `user_plot_leaders_pccp.py` | 17.1 x 23.3 cm (PCCP double column, max height), no suptitle | independent per panel | `ring_size_barriers.tiff` (600 dpi), `ring_size_barriers.pdf` |
| `user_plot_leaders_pccp_pair_y.py` | 17.1 x 23.3 cm, no suptitle | shared by the DFT / CNEO-DFT pair of each molecule | `ring_size_barriers_pair_y.tiff` (600 dpi), `ring_size_barriers_pair_y.pdf` |

The journal-size scripts draw the figure at its printed size: tick and axis
labels 8 pt, panel titles 9 pt, gutter labels 6 pt at a 7 pt pitch, so no
scaling is needed in LaTeX (`\includegraphics[width=\textwidth]` inside
`figure*`).

## Figures (`figures/`)

| File | From |
|---|---|
| `user_plot_with_mean.pdf`, `.png` | `user_plot_leaders.py` |
| `user_plot_with_mean_same_y.pdf`, `.png` | `user_plot_leaders_same_y.py` |
| `ring_size_barriers.pdf`, `.tiff`, `_preview.png` | `user_plot_leaders_pccp.py` |
| `ring_size_barriers_pair_y.pdf`, `.tiff`, `_preview.png` | `user_plot_leaders_pccp_pair_y.py` |

The TIFF files are 4038 x 5502 px with a 600 dpi tag (17.1 x 23.3 cm),
LZW-compressed, as requested by the RSC artwork guidelines; the PDFs are the
vector copies of the same figures; the `_preview.png` files are 150 dpi
renders for quick viewing.

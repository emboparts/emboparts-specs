# emboparts-specs

Machine-readable parameter tables for Chinese humanoid-robot joint modules and dexterous hands,
published by [EmboParts](https://emboparts.com). We source these lines and quote them daily, so
the tables are the same ones our customers get — no scraping of manufacturer PDFs.

**What is here**

| File | Contents |
|---|---|
| `data/tables.json` | Every parameter table on emboparts.com, verbatim: page, section, columns, rows |
| `data/joint-modules.csv` | The same torque tables, normalised into one flat file |

Tables cover Tongchuan (TC Drive / HarmoCore), Crabnova (Juxiedrive), EYOU, Ti5 Robotics and
DAMIAO: frame size Φ30–Φ170, rated torque 1.65–382 N·m, ratios 5:1 to 161:1, CAN / CAN FD /
EtherCAT options, and the dexterous-hand range from Linkerbot.

**Read the torque columns carefully.** Manufacturers label torque differently — *rated* is quoted
at a stated input speed or as an allowable average load, *peak start-stop* is what the gearbox
survives briefly, and *peak output* is the absolute ceiling. Comparing a rated figure against a
peak figure is the single most common selection error. Our site explains the distinction here:
<https://emboparts.com/glossary/rated-vs-peak-torque/>

**Accuracy.** Figures are transcribed from manufacturer datasheets and are *approximate*.
Confirm the exact configuration, firmware version and current rating with us before you design
around a number. Where a datasheet is silent the field is empty rather than guessed.

**Regenerate**

```bash
python build_github_repo.py
```

The script scrapes the generated site, so the data always matches what is published.

**License**

Data: CC BY 4.0 — use it commercially, just credit `EmboParts (emboparts.com)` and link back.
Code in this repository: MIT.

**Contact** — sales@emboparts.com · <https://emboparts.com>

# EMS Twin

## Reproduce

Place the original CSV files in `data/raw/` without changing them. From the repository root, run these two commands with Python 3.9 or later:

```bash
python src/load.py
python src/checks.py
```

`load.py` reads every CSV in `data/raw/`, writes a parsed CSV to `data/interim/`, and records row counts and source fingerprints in `data/interim/manifest.json`. `checks.py` reconciles the generated CSV records and counts against the original files and reports any mismatch. Both commands use only the Python standard library. Add the source CSVs before running; the commands exit with a clear error if none are present.

`data/raw/` is for untouched source files. `data/interim/` holds generated files. Both are ignored by Git and created automatically when the loader runs. Track assumptions and each work session in `log.md`; define actual source fields in `docs/data_dictionary.md` once the data is known. `notebooks/01_explore.ipynb` is scratch work, while the scripts and checks are the reproducible workflow.

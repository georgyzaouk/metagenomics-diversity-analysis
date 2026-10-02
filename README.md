# metagenomics-diversity-analysis

Automated and reproducible metagenomics workflow for 16S/18S extraction, quality control, OTU clustering, diversity analysis, BLAST-based taxonomy, and phylogenetic analysis.

## Repository structure

```text
.
├── pipeline.ipynb
├── requirements/
│   ├── apt-packages.txt
│   └── python-requirements.txt
├── .gitignore
└── README.md
```

## Setup

Install the Ubuntu/WSL packages:
```bash
sudo xargs -a requirements/apt-packages.txt apt install -y
```

Create a Python virtual environment:
```bash
python3 -m venv .venv
source .venv/bin/activate
```

Install the Python dependencies:
```bash
pip install -r requirements/python-requirements.txt
```

## Usage

Place the required data files in a data/ folder:
```text
.
├── pipeline.ipynb
├── data/
├── requirements/
├── .gitignore
└── README.md
```

then open:
```text
pipeline.ipynb
```

Run the notebook step by step.

Generated files are written to:
```text
results/
├── work/
└── logs/
```
- `work/` contains the generated analysis files.
- `logs/` contains the terminal output from each command.

After running the pipeline, the project structure will look like:
```text
.
├── pipeline.ipynb
├── data/
├── requirements/
├── .gitignore
└── README.md
```

## Workflow
```text
Raw reads
→ SortMeRNA
→ FastQC
→ Sickle
→ Seqtk
→ Mothur
→ BLAST / SILVA
→ ETE3
→ iTOL
```

The notebook is designed so that individual steps can be rerun independently.



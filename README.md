# UPXO Demos

Example Jupyter notebooks for [UPXO](https://github.com/Design-By-Fundamentals-UKAEA/UPXO) (UKAEA Poly-XTAL Operations), an open-source Python framework for generating, analysing, meshing and exporting polycrystalline grain structures.

- Main repository: https://github.com/Design-By-Fundamentals-UKAEA/UPXO
- Documentation: https://design-by-fundamentals-ukaea.github.io/UPXO/
- Wiki: https://github.com/Design-By-Fundamentals-UKAEA/UPXO/wiki

## Getting started

You need Python 3.13 or newer. A fresh virtual environment keeps things clean:

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
```

### Install UPXO

Pick one.

**1. Core install.** Enough for the grain structure generation and analysis demos.

```bash
pip install upxo
```

**2. Everything.** Adds all the optional extras below. This is the safe choice if you want to run any demo.

```bash
pip install "upxo[all]"
```

**3. Only the extras you need.**

| Extra | Adds | Command | Needed for |
|---|---|---|---|
| `mesh` | FE meshing (`gmsh`, `tetgen`) | `pip install "upxo[mesh]"` | the meshing demos, e.g. `confMesh/` and `tet_mesh_v2p1_A.ipynb` |
| `viz` | Interactive plots (Plotly) | `pip install "upxo[viz]"` | interactive plots |
| `ebsd` | EBSD data import (DefDAP) | `pip install "upxo[ebsd]"` | EBSD demos |

Extras can be combined, for example `pip install "upxo[mesh,viz]"`.

**4. From source** (if you want the latest development version of UPXO):

```bash
git clone https://github.com/Design-By-Fundamentals-UKAEA/UPXO.git
cd UPXO
pip install -e ".[all]"          # editable: changes in the clone take effect straight away
```

Use `pip install ".[all]"` instead for a normal, non-editable install from the clone. The [Getting Started wiki page](https://github.com/Design-By-Fundamentals-UKAEA/UPXO/wiki/Getting-started) has more on setting up environments.

A few things worth knowing:

- Meshing needs `gmsh`, and `gmsh` has no wheel for Linux on ARM (aarch64), so the `mesh` and `all` installs don't work there.
- If you hit `ModuleNotFoundError: No module named 'gmsh'`, you installed without the `mesh` extra. Run `pip install "upxo[mesh]"`.
- On Windows with long paths turned off, create the environment in a short path (the install can fail when `site-packages` is about 150 characters deep).

### Run the demos

```bash
pip install jupyterlab
git clone https://github.com/Design-By-Fundamentals-UKAEA/UPXO-demos.git
cd UPXO-demos
jupyter lab
```

Open a notebook and run it. Some notebooks read files that sit next to them (an Excel dashboard or a data folder). JupyterLab runs a notebook from its own folder, so that works as long as you open the notebook inside the cloned repo. If you run notebooks from another tool, set its working directory to the notebook's folder.

## Demos

Demo notebooks are being curated and will be added to this repository over time.

## Licence

The demos in this repository are released under the [MIT licence](LICENSE). The UPXO library itself is licensed separately; see the [main repository](https://github.com/Design-By-Fundamentals-UKAEA/UPXO). Copyright details are in [COPYRIGHT.md](COPYRIGHT.md).

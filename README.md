# Great Expectations Demo

Hands-on lab on **data validation with [Great Expectations (GX Core)](https://docs.greatexpectations.io/docs/core/introduction/try_gx/)**: connect to data, create expectations, validate a batch, and review the results using a sample of the NYC taxi trip dataset.

## Setup

The project is managed with [uv](https://docs.astral.sh/uv/). uv also downloads the right Python version (see `.python-version`), so you don't need to install Python yourself.

1. Install uv

2. Clone this repository and install the dependencies:

   ```bash
   git clone <repo-url>
   cd great_expectations_demo
   uv sync
   ```

## Run the notebook

Use either:

- **JupyterLab**: `uv run jupyter lab`, then open `great_expectations_demo.ipynb`.
- **VS Code**: open the folder, open the notebook, and choose the `.venv` interpreter as the kernel (*Select Kernel → Python Environments → .venv*).

## Part 2: unstructured data

`gx_unstructured_data.ipynb` shows that GX is not limited to tabular datasets. It downloads a cats vs. dogs image dataset (41 MB) from the [DVC dataset registry](https://github.com/treeverse/dataset-registry). Then it computes one row of **features per image** (format, color mode, size, brightness, content hash, ...) and validates that features table with an Expectation Suite. Finally it corrupts a copy of the images to show which problems GX catches. Run it the same way as the first notebook. The images are saved in `data/` (ignored by git).

## Generated files

The notebooks create a `gx/` folder (ignored by git) that holds the GX project. The **Data Docs** generated during the lab are in `gx/uncommitted/data_docs/local_site/index.html`; open that file in a browser. To start from scratch, delete `gx/`.

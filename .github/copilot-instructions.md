# Copilot Instructions for This Codebase

## Project Overview
This project demonstrates a basic machine learning workflow using ZenML and scikit-learn in a Jupyter Notebook. The main focus is on converting a simple model training script into a ZenML pipeline for reproducibility and modularity.

## Key Files
- `znml_basics.ipynb`: Main notebook containing all code and documentation. All logic, including data loading, model training, and pipeline conversion, is implemented here.

## Architecture & Workflow
- The workflow starts with a standard scikit-learn training script using the digits dataset and SVC classifier.
- The notebook then transitions to using ZenML, introducing `@step` and `@pipeline` decorators to modularize the workflow.
- All code is written and executed within the notebook; there are no separate Python modules or scripts.

## Patterns & Conventions
- **Notebook-first development**: All logic, including imports, function definitions, and ZenML pipeline construction, is in the notebook.
- **ZenML Usage**: Use `@step` to define modular steps and `@pipeline` to compose them. Example:
  ```python
  from zenml import step, pipeline

  @step
def load_data() -> ...:
      ...

  @pipeline
def training_pipeline(...):
      ...
  ```
- **Minimal external dependencies**: Only `zenml`, `scikit-learn`, and `numpy` are used. Install missing packages via notebook cells if needed.
- **No custom configuration files**: All configuration is done inline in the notebook.

## Developer Workflows
- **Run cells sequentially** to execute the workflow. Start with data loading, then model training, then pipeline conversion.
- **Debug in notebook**: Use print statements or cell-by-cell execution for debugging.
- **Add new steps** by defining new functions with the `@step` decorator.
- **Update the pipeline** by modifying the pipeline function and re-running the relevant cells.

## Integration Points
- **ZenML**: Used for pipeline orchestration. No advanced stack or artifact store configuration is present in this example.
- **scikit-learn**: Used for model training and evaluation.

## Example: Adding a New Step
To add a preprocessing step:
```python
@step
def preprocess_data(data):
    ...
```
Then update the pipeline definition to include this step.

## Additional Notes
- There are no tests, CI/CD, or build scripts in this project.
- All experimentation and development is intended to be interactive within the notebook.

---
_If you add new files, scripts, or workflows, update this file to reflect those changes._

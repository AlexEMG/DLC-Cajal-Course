# Action segmentation

## Installation:

First, install DLC2Action based on the <a href="https://github.com/amathislab/DLC2action#installation" target="_blank">installation guide.</a>

We note, that you can also use it in COLAB (see below), which requires no installation on your system.

## Using DLC2Action on an example labeled dataset

We prepared Jupyter Notebooks for going through an example dataset from Sturman et al. {cite}`Sturman2020`.

You can find the Notebook <a href="https://github.com/amathislab/DLC2action/blob/master/examples/minimal_notebook.ipynb" target="_blank">here</a>
Note you can also open and run this notebook with Colab.

## Advanced features

DLC2Action has many additional features, you can explore those by:

- checking out a more <a href="https://github.com/amathislab/DLC2action/blob/master/examples/demo_notebook.ipynb" target="_blank">detailed notebook</a> (also based on the Sturman et al. data). Note you can also open and run this notebook with [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/amathislab/DLC2action/blob/master/examples/demo_notebook.ipynb).
- or checking out the <a href="https://amathislab.github.io/DLC2action/html_docs/dlc2action.html" target="_blank">documentation</a>

## Running DLC2Action on your data

You will need to have some annotation data. DLC2action accepts many different formats. If you have not yet annotated any behaviors, then you can use the following <a href="https://github.com/amathislab/dlc2action_annotation" target="_blank">GUI</a>.

```{note}
For good performance you will need to annotate multiple examples for each behavior that you are interested in. This will usually take a bit of time!
```

## Basic Workflow (Python commands)

**Import DLC2Action**
```python
from dlc2action.project import Project
```

**(1) Create a project 📂**
```python
PROJECT_NAME = "test"  # the name of the project
PROJECTS_PATH = ...  # the path to the projects folder
DATA_TYPE = ...  # choose from Project.print_data_types()
ANNOTATION_TYPE = ...  # choose from Project.print_annotation_types()
DATA_PATH = ...  # path to data files
ANNOTATION_PATH = ...  # path to annotation files

FILE_PATHS = (
    None  # set to a list of file paths if you want to generate predictions for new data
)

project = Project(
    PROJECT_NAME,
    projects_path=PROJECTS_PATH,
    data_type=DATA_TYPE,
    annotation_type=ANNOTATION_TYPE,
    data_path=DATA_PATH,
    annotation_path=ANNOTATION_PATH,
)

# run project.help() for general information
# and project.help("data") to make sure that your files are organized correctly
```

**(2) Update parameters (model, learning rate, etc.) **

```python
project.update_parameters(
    ...
)  # run project.list_blanks() to see which parameters you need to update

MODELS = [
    "c2f_tcn",
    "transformer",
]  # see project.help("models") for a list of available models
```

**(3) Perform hyperparameter search and train your model**

```python
for model in MODELS:  # run a hyperparameter search for your models
    project.run_default_hyperparameter_search(
        f"{model}_search",
        model_name=model,
        metric="f1",
    )

for model in MODELS:  # train models with the best hyperparameters
    project.run_episode(
        f"{model}_best",
        load_search=f"{model}_search",
        parameters_update={"general": {"model_name": model}},
        n_seeds=3,
        force=True,
    )

project.plot_episodes(  # compare training curves
    [f"{model}_best" for model in MODELS],
    metrics=["f1"],
    title="Best model training curves",
)
```


**(4) Evaluate your model**

```python
for model in MODELS:  # evaluate more metrics
    project.evaluate(
        [f"{model}_best"],
        parameters_update={
            "general": {"metric_functions": ["segmental_f1", "pr-auc", "f1"]},
            "metrics": {"f1": {"average": "none"}},
        },
    )

project.get_results_table(
    [f"{model}_best" for model in MODELS]
)  # get a table of the results

BEST_MODELS = [MODELS[0], MODELS[1]]  # choose the best model

project.run_prediction(
    [
        f"{model}_best" for model in BEST_MODELS
    ],  # if you choose multiple models, the predictions will be averaged
    force=True,
    file_paths=FILE_PATHS,  # make a prediction for new data
)

project.list_episodes(  # get the experiment history
    display_parameters=[
        "results/f1",
        "meta/time",
        "meta/training_time",
        "general/model_name",
    ],
    value_filter=f"results/f1::>0.3,general/model_name::{BEST_MODELS[0]}",
)
```

````{admonition} References
:class: seealso
```{bibliography}
:filter: docname in docnames
```
````

[Let’s go back 🔙](Day4_Practicals.md).

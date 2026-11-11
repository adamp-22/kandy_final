# Kandy — Phase 1 report

Can small image changes fool an AI-image detector? We compare a CNN trained from scratch with a ResNet18 trained further on CIFAKE.

Adam and Gabor both worked on the human and AI-assisted parts of the project because the other two group members dropped out.

## Notebooks

Open these in order:

1. [Data exploration](phase1/01_data_exploration.ipynb)
2. [CNN training and visualizations](phase1/02_cnn_training_and_visualization.ipynb)
3. [ResNet18 training and visualizations](phase1/03_resnet18_finetuning_and_visualization.ipynb)

The saved outputs are visible on GitHub. The notebooks include training code, learning curves, model selection, and the results after changing the images.

## Report and presentation

- [AI-assisted visualization report](ai_reflection_midpoint.md)
- [Five-minute presentation](presentations/Phase_1_5min.pptx)
- [Speaking script](presentations/Phase_1_5min_script.md)
- [Team information](team-info.json) and [workload split](workload.json)

## Running the notebooks

Install the packages with `python -m pip install -r requirements.txt`, then open the notebooks in Jupyter or VS Code.

Run All uses the saved results in `phase1/data/`. It does not need the full dataset or trained weights. [The data guide](phase1/data/README.md) explains the saved files.

To train again, download [CIFAKE](https://www.kaggle.com/datasets/birdy654/cifake-real-and-ai-generated-synthetic-images). Put its `train/` and `test/` folders in `data/cifake/`, run `python phase1/prepare_data.py` from this folder, and set `RUN_TRAINING = True` in a model notebook. New runs save to their own folders. The submission plots continue to show the recorded experiment.


## Team

| Name | GitHub |
| --- | --- |
| G.L. | [LordNassel](https://github.com/LordNassel) |
| Adam Parkanyi | [adamp-22](https://github.com/adamp-22) |

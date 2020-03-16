Status:
=======

- random baseline model provided by Allen AI setup, ran and tested

- wilburOne's baseline model setup in progress

- research paper reading in progress

___

Guide to setup cosmos conda environment
---------------------------------------

Installing and creating conda environment:

- Get the installer from here: https://docs.conda.io/en/latest/miniconda.html, install conda (make sure it is available in $path)

- Redirect to github project base directory in command line

- Execute: `conda env create -f conda-env.yml` # this will install required project dependencies

- Activate environment: `conda activate cosmos` # this will activate conda environment


Updating conda environment:

- In order to update depdendencies, add that dependency in conda-env.yml file and run `conda env update -f conda-env.yml`

Deleting conda environment:

- `conda deactivate`

- `conda env remove -n cosmos`

___

Running cosmosqa_baseline:
--------------------------
This random baseline is provided by [Allen AI](https://leaderboard.allenai.org/cosmosqa/submissions/public) for demonstrating input and output of data. ([GitHub](https://github.com/allenai/mosaic-leaderboard/tree/master/cosmosqa))

Make sure you have activated cosmos conda environment

Run random model:
`python ./cosmosqa_baseline/baselines/random-baseline/random_baseline.py --input-file ./official_data/train.jsonl --output-file ./results/random_predictions.lst`

Evaluate random model:
`python ./cosmosqa_baseline/evaluator/eval.py --labels_file ./official_data/train-labels.lst --preds_file ./results/random_predictions.lst --metrics_output_file ./results/random_metrics.json`



# LongevityInterpolant
This repository contains the data, code, and supporting files for interpolating functions for longevity outome variables based on a set of feature variables that were inputs to the simulation process using the OG-USA macroeconomic model.

We have included the Jupyter notebook [`SeparateCSVs.ipynb`](https://github.com/OpenRG/LongevityInterpolant/blob/main/code/SeparateCSVs.ipynb) in the [`/code`](https://github.com/OpenRG/LongevityInterpolant/tree/main/code) directory of this repository. This notebook uses the master data file for the surrogate model from [`all_sources_together.csv`](https://github.com/OpenRG/LongevityInterpolant/blob/main/data/all_sources_together.csv) and creates 6 separate `.csv` files, one for each interpolation model. We have 6 outcome variables of interest, listed down the left column of the following table, which we are predicting from the feature variables in the next 7 columns of the table. Only model 6 that predicts the `NPV` variable is a function of all 7 feature variables. Model 6 is the only model that includes the `discount_rate` variable as a feature variable. All the other models (models 1 - 5) are only functions of the first 6 feature variables.

| Model <br> num | Response <br> variable | Feature variable <br> `age_effect` | Feature variable <br> `initial_effect` | Feature variable <br> `final_effect` | Feature variable <br> `mort_effect` | Feature variable <br> `prod_effect` | Feature variable <br> `fert_effect` | Feature variable <br> `discount_rate` | Observations | CSV filename |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| 1 | `pop_diffs_2045_2065` | Yes | Yes | Yes | Yes | Yes | Yes | No |    472 | `model1_pop2045.csv`  |
| 2 | `pop_diffs_2025_2100` | Yes | Yes | Yes | Yes | Yes | Yes | No |    472 | `model2_pop2025.csv`  |
| 3 | `pop_diffs_2050`      | Yes | Yes | Yes | Yes | Yes | Yes | No |    472 | `model3_pop2050.csv`  |
| 4 | `avg_diff`            | Yes | Yes | Yes | Yes | Yes | Yes | No |    472 | `model4_avgdiff.csv`  |
| 5 | `avg_gdp_pc_diff`     | Yes | Yes | Yes | Yes | Yes | Yes | No |    472 | `model5_avggdppc.csv` |
| 6 | `NPV`                 | Yes | Yes | Yes | Yes | Yes | Yes | Yes | 2,832 | `model6_npv.csv`      |

In the `.csv` data files listed in the last column of the table above, which are created in the cells below, each row is an observation and each column is a variable. The first column of the `.csv` file is always the predicted variable for the model, one of the variables from the first column of the table above. Then the following columns of the `.csv` file are the feature variables. The first row of the `.csv` file contains the variable names. All data `.csv` files in the last column of the table above are stored in the [`/data/`](https://github.com/OpenRG/LongevityInterpolant/tree/main/data) folder of the GitHub repository for this project at https://github.com/OpenRG/LongevityInterpolant.

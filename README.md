# XGBoost Model for Inferring C-VOD (AMSR2) Using IFS fields and Copernicus LAI
### Keywords: Emulation of satellite observations, Leaf Area Index, Passive Microwave Remote Sensing, Vegetation Optical Depth, Vegetation dynamics, XGBoost.

This repository provides a Jupyter Notebook to infer C-band Vegetation Optical Depth (C-VOD) using Integrated Forecast System (IFS) fields and Copernicus Leaf Area Index (LAI) as inputs. The model leverages XGBoost, a scalable and efficient machine learning algorithm, to predict C-VOD, which plays a critical role in understanding vegetation dynamics.

## What is C-VOD?
C-band Vegetation Optical Depth (C-VOD) is a parameter derived from passive microwave remote sensing that quantifies the attenuation of microwave radiation caused by vegetation. It is derived at the C-band wavelength of 6.925 GHz from AMSR2 (Advanced Microwave Scanning Radiometer 2) sensor.

C-VOD is sensitive to:
- Vegetation water content: The amount of water held within vegetation, including leaves, stems, and branches.
- Biomass structure: The density and distribution of vegetation.
- Vegetation type: Different vegetation types (e.g., crops, forests) influence C-VOD values.

## Features
- Input Data: The model leverages IFS and Copernicus LAI datasets.
IFS (Integrated Forecast System) fields provide crucial meteorological and environmental data, including:
  - Soil moisture: Directly affects vegetation water content.
  - Temperature: Impacts vegetation growth and stress.
  - Precipitation: A key driver of vegetation dynamics.
  - Radiation fluxes: Determines photosynthesis rates and energy exchange.
- Copernicus LAI (Leaf Area Index): Measures vegetation canopy structure, a fundamental input for assessing vegetation health and biomass.

## Repository Structure
- xgb_c-vod.ipynb: Jupyter Notebook containing the complete workflow:
  - Data loading and preprocessing.
  - Feature engineering using IFS fields and LAI.
  - Training the XGBoost model.
  - Evaluating and interpreting the results.
- training_sample-201901-201903-8d_9km.zarr.zip: Contains sample training dataset in compressed format.
- test_sample_202101-8d_9km.zarr.zip: Contains sample testing dataset in compressed format.

## Getting Started
Follow these steps to set up and run the project:

#### 1. Clone the Repository
   
    git clone https://github.com/selgarroussi/fuelity.git
    cd fuelity

#### 2. Prerequisites

- Ensure you have the following installed:
  - Python 3.7+
  - Jupyter Notebook or Jupyter Lab
  - Required Python libraries (listed in requirements.txt)

- Install dependencies with:

      pip install -r requirements.txt

#### Dependencies

Key libraries required for this project:

    anemoi-datasets
    xgboost
    numpy
    pandas
    scikit-learn
    matplotlib

Install all dependencies using the requirements.txt file.

#### 3. Prepare the Data

- Download the sample data from the repository or provided link.

- Decompress the training and testing datasets locally (e.g., using tar, zip, or other tools).

- Update the file paths in the notebook to point to the decompressed files.

##### Example:

    # Update path to the location of the decompressed or new datasets
    train_data_path = "/path/to/decompressed/train_data/training_sample-201901-201903-8d_9km.zarr"
    test_data_path = "/path/to/decompressed/test_data/test_sample-202101-8d_9km.zarr"

#### 4. Run the Notebook

- Launch the Jupyter Notebook:

        jupyter notebook

- Open the notebook file (xgb_c-vod.ipynb) and run the cells sequentially.

#### Notebook Workflow

- Data Loading: Load the training and test datasets after updating file paths.

- Preprocessing: Perform any necessary data cleaning and preparation.

- Model Training: Train an XGBoost model on the training dataset.

- Evaluation: Evaluate model performance on the test dataset.

- Predictions: Generate predictions for unseen data.

#### Applications and Future Extensions
This model can be applied in various domains:

- Real-time monitoring: Inferring C-VOD using updated meteorological inputs.
- Scenario analysis: Simulating vegetation dynamics under changing climatic conditions.
- Regional and global studies: Analysing vegetation responses across different ecosystems.
  
Future work could involve:
- Incorporating additional remote sensing datasets.
- Extending the model to predict vegetation conditions at other frequencies or spatial resolutions.

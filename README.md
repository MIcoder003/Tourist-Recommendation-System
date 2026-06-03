# Travel Recommendation System

A simple experimental recommender system for Tokyo tourism destination data.

This repository contains a notebook that loads a cleaned Tokyo check-in dataset, converts visit timestamps into stay durations, builds implicit user-item ratings from stay time, and generates user-based collaborative filtering recommendations.

## Contents

- `Main.ipynb` - Jupyter notebook with the preprocessing and recommendation pipeline.
- `tokyo_clean.csv` - Cleaned data file containing user visits, location coordinates, and timestamps.

## What it does

The notebook performs these main steps:

1. Loads the Tokyo tourism dataset.
2. Sorts and maps original user IDs to numeric user IDs.
3. Maps locations (latitude/longitude) to numeric item IDs.
4. Computes stay duration for repeated visits at the same location.
5. Converts stay durations into normalized ratings per item.
6. Builds a user-item rating matrix.
7. Uses user-based collaborative filtering to recommend new locations.

## How to run

### In Google Colab

1. Open `Main.ipynb` in Colab.
2. Mount Google Drive if needed.
3. Update the dataset path in the notebook if the file is not in the same Drive location.

### Locally

1. Install Python dependencies:
   - `numpy`
   - `pandas`
   - `scipy`
2. Open `Main.ipynb` in your local notebook environment.
3. Adjust the dataset path in the notebook to point to `tokyo_clean.csv` in this repository.

## Notes

- The notebook currently expects the dataset path used in a Colab environment.
- Ratings are derived from normalized stay duration, not from explicit user ratings.
- Recommendations are generated using a nearest-neighbor method over users.

## Improvements

Possible enhancements include:

- fixing the time-difference calculation to handle multi-day visits and missing timestamps
- using a local dataset path rather than a hard-coded Drive path
- adding evaluation metrics for recommendation quality
- supporting item-based filtering or matrix factorization

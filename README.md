# NYC Taxi Fare Prediction: Big Data (PySpark + Parquet Data Lake) + Neural Networks

Integrated CA1: Advanced Data Analytics (Neural Networks) + Big Data Storage & Processing.

## Research question
How accurately can a neural network (with learned zone embeddings), trained on features produced by a PySpark + Parquet
data lake pipeline, predict taxi fare compared with traditional baselines (linear regression, random forest),
and how does the pipeline behave as data volume grows?

## Pipeline stages (one notebook per stage)
| Stage | Notebook | What it does |
|-------|----------|--------------|
| 1 | notebooks/01_data_ingestion_storage.ipynb | download TLC data, load in Spark, write partitioned Parquet raw zone |
| 2 | notebooks/02_data_preparation.ipynb | cleaning, missing values, duplicates, outliers, features, train/val/test split |
| 3 | notebooks/03_big_data_processing_pyspark.ipynb | architecture, Spark SQL analytics, scalability tests, modelling sample |
| 4 | notebooks/04_baseline_model.ipynb | mean predictor, linear regression, random forest, baseline NN |
| 5 | notebooks/05_experiments_iterations.ipynb | Exp1-Exp5 iterations and comparison |
| 6 | notebooks/06_final_model_evaluation.ipynb | final model, one-time test evaluation, error analysis |
| Final | notebooks/Final_Integrated_CA.ipynb | all stages merged (submit this to Moodle) |

Shared code: `src/utils.py`. Results (tables, figures, logs): `results/`. Report helpers: `report/`.

## Dataset
NYC TLC Yellow Taxi Trip Records (Parquet), Jan-Mar 2024 (about 9-10 million trips).
- Official page: https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page
- Direct file pattern (used by notebook 01): `https://d37ci6vzurychx.cloudfront.net/trip-data/yellow_tripdata_2024-01.parquet`
- Zone lookup: `https://d37ci6vzurychx.cloudfront.net/misc/taxi_zone_lookup.csv`
- Notebook 01 downloads everything automatically. Upload the files to Google Drive (sharing: anyone with the link) and put the link below.

Google Drive link (datasets + screencast): ADD LINK HERE

## Run (Google Colab recommended)
```
!pip install pyspark==3.5.1 pyarrow
```
Then run the notebooks in order (Colab already has TensorFlow, pandas, scikit-learn, Java).
Locally: `pip install -r requirements.txt` and Java 8/11/17.
If memory is low, reduce `MONTHS` in notebook 01 to `[1]` and `FRAC` in notebook 03 to `0.1`.

## Git
Commit after you really finish each stage. See `report/COMMIT_GUIDE.md`.

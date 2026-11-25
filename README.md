# Big Data Projects: MongoDB and Apache Spark

Two class projects from a graduate big data management course (DSCI 531, Grove City College, Spring 2026). Course work, shared for reference. Please don't reuse it as a course submission.

| Project | Stack | Notebook |
|---|---|---|
| Movie ticket sales pipeline | MongoDB Atlas, PyMongo, pandas, matplotlib | [`mongodb/ticket_sales_pipeline.ipynb`](mongodb/ticket_sales_pipeline.ipynb) |
| Grocery order analytics | PySpark on Databricks | [`spark/CreateTable.ipynb`](spark/CreateTable.ipynb), [`spark/KPIs.ipynb`](spark/KPIs.ipynb) |

## MongoDB: ticket sales pipeline

- Atomic seat purchase: one guarded `update_one` so two buyers can't take the last seats
- Aggregation pipelines that build reporting collections by movie and by genre (`$merge`)
- Dashboard charts in pandas and matplotlib
- Archives one older movie's sales out of the working collection

Set the `MONGODB_URI` environment variable to your Atlas connection string. The notebook expects a database named `Mongo_Project`.

## Spark: grocery order analytics

- `CreateTable.ipynb` joins five Instacart Parquet tables into one curated `order_details` table
- `KPIs.ipynb` computes KPIs from it: department volume, reorders by hour, basket size and product trends

Run `CreateTable` first, since `KPIs` reads the table it saves. Update the Parquet paths for your own Databricks volume.

## Data

Neither dataset is included. The ticket sales data was provided by the course. The Spark project uses the Instacart Online Grocery Shopping Dataset (2017), and its own terms apply.

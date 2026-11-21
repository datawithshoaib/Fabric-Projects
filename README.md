# Microsoft Fabric Projects

End-to-end data engineering projects built on Microsoft Fabric. Each project follows a layered lakehouse / warehouse design and ends in data ready for Power BI.

## Projects

### [Worldwide Earthquake Events](Earthquake-Data-Project/)

A medallion pipeline over the USGS Earthquake API.

- **Bronze:** a Python notebook pulls raw earthquake events from the API and stores the JSON.
- **Silver:** PySpark cleans, types and flattens the events.
- **Gold:** PySpark aggregates the data for analytics and reporting.

**Stack:** Fabric Lakehouse, notebooks, PySpark, Python `requests`.

### [NYC Yellow Taxi](NYC-Yellow-Taxi-Data-Project/)

A production-style pipeline for NYC Yellow Taxi trips (January to October 2025).

- Monthly Parquet files land in a Fabric Lakehouse.
- Raw data loads into a Warehouse staging layer, is cleansed and validated, and is enriched with the taxi zone lookup.
- A presentation layer models the data, keeps full history (append model) and logs per-run metadata for auditability.
- Metadata-driven Data Factory pipelines automate the month-over-month run.
- A Fabric semantic model exposes the data to Power BI.

**Stack:** Fabric Data Factory, Lakehouse, Warehouse, Dataflows Gen2, SQL stored procedures, Power BI.

## Using these projects

Each project folder has its own README with setup steps, pipeline definitions and screenshots. Import the notebooks into a Fabric workspace attached to a Lakehouse to run them.

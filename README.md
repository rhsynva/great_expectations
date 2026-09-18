
1. Package Setup: I installed `great_expectations` version 1.20.0 and imported `pandas` alongside the Great Expectations modules.
2. Data Loading: I ingested the 2019 NYC Yellow Taxi sample dataset (`yellow_tripdata_sample_2019-01.csv`) into a Pandas DataFrame.
3. Great Expectations Context Configuration: I established an ephemeral context with `gx.get_context()`, registered a Pandas data source, attached a DataFrame asset named `pd dataframe asset`, and defined a whole-dataframe batch definition.
4. Batch Processing: I generated a batch using the target DataFrame for validation testing.
5. Quality Expectation Definition: I configured an expectation (`ExpectColumnValuesToBeBetween`) targeting the `passenger_count` column, setting a acceptable range between 1 and 6.
6. Execution and Verification: I validated the batch against the expectation rule, achieving a successful result with 0 unexpected records across 10,000 rows.

---

# Data Quality Validation Pipeline with Great Expectations

This repository demonstrates how I set up automated data quality testing using Great Expectations and Pandas.

## Project Overview

I built this project to test tabular data against pre-defined data quality assertions. The pipeline downloads raw CSV data, establishes an ephemeral Great Expectations context, defines structural expectations for specific columns, and validates dataset integrity before downstream analysis.

## Key Features

1. Automated data quality validation using Great Expectations v1.x syntax.
2. Direct integration with Pandas DataFrames.
3. Configurable expectation rules to catch boundary violations and unexpected values.

## Workflow Breakdown

1. Environment Preparation: I install Great Expectations and load necessary dependencies.
2. Data Ingestion: I load the 2019 NYC Yellow Taxi sample dataset directly into Pandas.
3. Context Setup: I configure an ephemeral context (`gx.get_context()`), attach a Pandas data source, and register a batch definition.
4. Rule Definition: I create an expectation enforcing that the `passenger_count` column strictly contains numeric values between 1 and 6.
5. Validation: I execute `batch.validate()` to confirm data compliance and review validation statistics.

## Requirements

1. Python 3.10 or higher
2. pandas
3. great_expectations

## Getting Started

1. Clone my repository to local storage.
2. Install dependencies:

```bash
pip install great_expectations pandas

```

3. Open the Jupyter Notebook and execute all cells in order to run the validation check.

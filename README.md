# Project: No-Code Stock Price Prediction using Amazon SageMaker Canvas

## Objective
To build a time-series forecast model for stock prices using historical data from Yahoo finance API, focusing specifically on TESLA and NVIDIA stocks, and to visualize predictions using Amazon QuickSight.

## Prerequisites
- AWS account
- Basic understanding of stock market concepts

## Tools Used
- Amazon SageMaker Canvas
- Amazon QuickSight
- Amazon S3

## Steps Overview

### Part 1: Configuring Prerequisites & Obtaining a Dataset
1. **Create a SageMaker Domain**:
   - Log into AWS Console.
   - Navigate to SageMaker and set up a new domain under a specific AWS region.
   - Establish permissions via IAM roles, allowing access to necessary S3 buckets.

2. **Download Historical Data**:
   - Access Nasdaq and download the maximum available historical data for AAPL.
   - Adjust the dataset by renaming columns to `MarketClose`, `MarketOpen`, etc., and ensure all numerical fields are formatted correctly.

3. **Upload Data to S3**:
   - Either create a new S3 bucket or use an existing one.
   - Upload the prepared CSV file to the bucket.

### Part 2: Building Predictions with SageMaker Canvas
1. **Launch SageMaker Canvas**:
   - Open the SageMaker domain and launch the Canvas application.
   - Import the dataset from S3 into Canvas.

2. **Configure and Train the Model**:
   - Initiate a new model and select the uploaded dataset.
   - Choose `MarketClose` as the target column.
   - Set up the time-series model specifying `Ticker` for item identification and `Date` for timestamps.
   - Choose either a quick build for rapid prototyping or a standard build for more accurate results.

### Part 3: Generating Predictions
1. **Analyze Model Performance**:
   - Assess the model's accuracy and performance metrics on the test set within Canvas.

2. **Generate Forecasts**:
   - Define the forecast window to 30 days.
   - Produce and review probabilistic forecasts (P10, P50, P90).

### Part 4: Visualizing Predictions with QuickSight
1. **Setup QuickSight**:
   - Create a new dataset in QuickSight by uploading the prediction results.
   - Apply filters to exclude non-working days and zero values.

2. **Create Dashboard**:
   - Use a line chart to visualize the forecasts.
   - Configure axes and values to display the prediction intervals accurately.

## Conclusion
This project illustrates the capability of no-code platforms to make machine learning accessible to a broader audience. It provides a step-by-step guide to building and visualizing predictive models for stock prices.

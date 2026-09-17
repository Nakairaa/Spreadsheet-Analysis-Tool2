# CSV Data Analytics

Multi-dataset analysis tool for sales and product pricing data using Python and CSV parsing.

## Project Overview

This project demonstrates proficiency in Python fundamentals including CSV file handling, data collection into lists and dictionaries, conditional logic, and functional programming with lambda expressions. The tool analyses two separate datasets (sales records and car pricing) with dataset-specific analysis functions.

## Features

- **Multi-dataset support**: Choose between sales or car pricing datasets
- **Sales analysis**: 
  - View raw sales dataset
  - Calculate monthly sales breakdown
  - Calculate total sales across all months
- **Car pricing analysis**:
  - View raw car dataset  
  - Identify top N most expensive cars by selling price
- **Interactive menu**: User prompts guide selection between datasets and analysis options
- **Data validation**: Lambda functions and conditional checks validate numeric data

## How It Works

### Sales Workflow
1. Load sales.csv using csv.DictReader
2. User selects analysis type via menu
3. Functions aggregate sales by month or calculate totals
4. Results printed to console

### Car Pricing Workflow
1. Load car_prices.csv using csv.DictReader
2. User specifies how many top cars to display
3. Lambda function sorts cars by selling price (highest to lowest)
4. Top N cars displayed with make, model, and price

## Installation & Usage

### Prerequisites
- Python 3.x
- CSV files: `sales.csv` and `car_prices.csv` in project directory

### Run the Program
```bash
python3 data_analyser.py
```

### Interactive Menu
```
Select dataset: 'sales' or 'car'
Select analysis:
  Sales: [1] View dataset [2] Monthly breakdown [3] Total sales
  Car: [1] View dataset [2] Top N expensive cars
```

## Code Structure

**Main Function:**
- `read_data()` - User prompts, file loading, function selection via dictionary mapping

**Sales Analysis Functions:**
- `run_sales_by_month(sales_data)` - Groups sales by month, prints pairs of (month, total)
- `run_total_sales(sales_data)` - Sums all sales values, prints total

**Car Analysis Functions:**
- `top_n_expensive_cars(car_data)` - Filters valid prices, sorts descending, returns top N

**Key Techniques:**
- `csv.DictReader()` for parsing CSV files
- List and dictionary data structures for storing rows
- Lambda function for sorting: `lambda x: int(x['sellingprice'])`
- Function mapping dictionary for dynamic function selection
- Conditional logic for dataset-specific workflows

## Dataset Requirements

### sales.csv Format
```
month,sales
January,5000
February,7200
...
```

### car_prices.csv Format
```
make,model,sellingprice
Toyota,Corolla,15000
BMW,330i,45000
...
```

## Example Output

**Sales Analysis:**
```
Available options are:
1 The sales dataset
2 The total sales for each month
3 The total sales in that year

Select 1, 2 or 3: 2
The sales for each month are as follows:
[('January', 5000), ('February', 7200), ...]

Total sales: 45600
```

**Car Analysis:**
```
Available functions are:
1 The car dataset
2 The top most expensive cars

Select 1 or 2: 2
How many do you want to view?: 5

BMW 750i - £65000
Mercedes-Benz S-Class - £62000
Porsche 911 - £95000
...
```

## Skills Demonstrated

- CSV file I/O with csv.DictReader
- Data structures: lists, dictionaries, tuples
- Lambda functions for sorting
- Function mapping and dynamic function selection
- Conditional logic and user input handling
- Data aggregation and summation
- String formatting and output display
- Type conversions (int, float)


## Future Enhancements

- CSV output capability to save analysis results
- Error handling for missing/malformed CSV files
- Reusability for additional datasets (property listings, weather data, etc.)
- Data visualisation
- Unit tests for analysis functions
-  Sales Performance Automation
- Automated Data Validation & Quality Checks
- Business Insight & Anomaly Detection
- End-to-End Data Processing & Reporting Pipeline

## Files

- `data_analyser.py` - Main program
- `sales.csv` - Sample sales dataset
- `car_prices.csv` - Sample car pricing dataset
- `README.md` - This file
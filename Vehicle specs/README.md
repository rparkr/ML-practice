# Data Collection: Vehicle Info
> An exercise for my Machine Learning in Python course, to gather data to be used for running machine learning models. 

**Created by:** [Ryan Parker](https://github.com/rparkr)

**Updated on:** 13-Nov-2021

---

## About this repository
* `ML_Models_Vehicle_Specs.ipynb:` Jupyter notebook with my Python code to run 3 different kinds of machine learning models on the dataset.
* `Data_Collection_Vehicle_Info.ipynb`: The Jupyter notebook with my Python code to collect vehicle specs data from CarAndDriver.com
* `vehicle_specs.csv`: Main output of the Jupyter notebook; the set of vehicle specs data collected. Contains data on about 3,300 model-trims for the latest-model vehicles, from CarAndDriver.com's vehicle specs pages. Has over 40 columns of data on each trim, which are described below.
* `model_urls.csv`: List of around 800 models available on CarAndDriver.com's New Vehicles pages (by make, or automaker)
* `Make_2021_Domestic_Content.csv` and `Models_2021_Domestic_Content.csv`: supporting files used by the Jupyter notebook to add two columns to the output: Vehicle Origin (domestic vs. foreign), and Pct_domestic_content (the percent of component parts and labor, by value, that came from the U.S. or Canada). See Data Sources below for more info about this source.

---

## Data Sources
* Vehicle specs: [CarAndDriver.com](https://www.caranddriver.com/volkswagen/atlas/specs/2021/volkswagen_atlas_volkswagen-atlas_2021/417662)
* Vehicle origin: Percent of Vehicle Content from North America (US/Canada), [data from the NHTSA American Automobile Labeling Act](https://www.nhtsa.gov/part-583-american-automobile-labeling-act-reports)
 * [PDF for model year 2021](https://www.nhtsa.gov/sites/nhtsa.gov/files/2021-06/MY2021-AALA-Alphabetical-6-30-21.pdf) passenger vehicles
 * Converted PDF to Excel using [Adobe Acrobat free PDF to Excel converter](https://www.adobe.com/acrobat/online/pdf-to-excel.html), then heavily cleaned in Excel prior to saving as a .csv file for import in this notebook

**Other interesting data (not used here, but related)**
* [GoodCarBadCar.net](https://www.goodcarbadcar.net/2021-us-vehicle-sales-figures-by-model/), model-level vehicle sales data by year
* [List of new vehicle models and makes](https://www.kbb.com/car-make-model-list/new/view-all/make/), from Kelley Blue Book
* FuelEconomy.gov, the EPA's official source for vehicle fuel economy data. Available as a [CSV download](https://www.fueleconomy.gov/feg/download.shtml), with over 44k rows of data and [83 columns](https://www.fueleconomy.gov/feg/ws/index.shtml#vehicle), and also as a [Web Services API](https://www.fueleconomy.gov/feg/ws/index.shtml). Contains data for vehicle models from 1984-present

## Background
When searching for vehicles on Google (e.g., "[2021 Honda Civic](https://www.google.com/search?q=2021+honda+civic)"), I noticed that Google presented summarized specs for a vehicle (like weight, length, number of seats, and towing capacity) which were sourced from CarAndDriver.com. Car and Driver maintains comprehensive vehicle statistics for hundreds of models and trim levels for vehicles produced within the past few years.

This Jupyter Notebook walks through my process to collect and organize data from CarAndDriver.com to use for testing machine learning models.

## Data collected
**General info**
* Year
* Make
* Model
* Image URL
* Style (configuration)
* Trim
* Origin (domestic or foreign)
* Price (starting MSRP)
* EPA classification (vehicle class)

**Engine**

* Drivetrain (rear/front-wheel drive or AWD)
* Engine type
* Fuel type
* Engine displacement (L)
* Engine displacement (in $^3$)
* Max horsepower
* RPM for max HP
* Max torque
* RPM for max torque
* Transmission type
* Transmission speeds (gears)

**Fuel economy**

* CO $_2$ emissions (in tons)
* Range, city (miles)
* Range, highway (miles)
* MPG, combined
* MPG, city
* MPG, hwy
* Fuel tank capacity (gallons)

**Dimensions**

* Wheelbase (inches)
* Length (inches)
* Width, without mirrors (inches)
* Height (inches) 
* Ground clearance (inches)
* Turning diameter (feet)
* Front wheel size (inches)
* Rear wheel size (inches)
* Seating capacity
* Total passenger volume (ft $^3$)
* Cargo space (ft $^3$)
* Curb weight (pounds)
* GVWR (pounds)
* Payload capacity (pounds)
* Towing capacity (pounds)

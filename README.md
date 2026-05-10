# Global COVID-19 Analytics Dashboard

An interactive Shiny dashboard that visualizes global COVID-19 death rates and vaccination percentages, exploring the relationships between vaccination coverage and mortality across countries and continents.

## 📊 Live Demo

**Access the deployed app:** [COVID-19 Analytics Dashboard on shinyapps.io](https://8etlvn-devashree-pawar.shinyapps.io/COVID19Analysis/)

## 🎯 Research Questions

This dashboard addresses the following key questions:

1. **RQ1:** How do COVID-19 death rates vary across countries globally?
2. **RQ2:** Is there a relationship between vaccination rates and COVID-19 death rates?
3. **RQ3:** How do vaccination rates and mortality rates differ by continent?
4. **RQ4:** What is the global distribution of vaccination rates by mortality level?

## 📁 Project Structure

```
.
├── app.R                              # Main Shiny application
├── death_table.csv                    # COVID-19 death rates by country
├── vaccine_percent.csv                # Global vaccination percentages
├── vaccine_table.csv                  # Vaccine type information
├── HW4_DevashreePawar.Rmd            # R Markdown homework submission
├── README.md                          # This file
└── rsconnect/                         # Deployment configuration
```

## 🚀 Features

### Dashboard Tabs

- **Overview** - Research questions and project overview
- **Death Rates Map** - Choropleth map visualizing COVID-19 mortality by country
- **Vaccination vs. Mortality** - Scatter plot with regression analysis and continent filtering
- **Continental Analysis** - Box plots comparing vaccination rates and death rates across continents
- **Vaccination Distribution** - Histogram comparing vaccination rates for high/low mortality countries

## 📦 Requirements

### R Packages

```
shiny
shinydashboard
dplyr
ggplot2
rnaturalearth
rnaturalearthdata
sf
stringr
countrycode
```

### Installation

Install required packages:

```r
install.packages(c("shiny", "shinydashboard", "dplyr", "ggplot2", 
                   "rnaturalearth", "rnaturalearthdata", "sf", "stringr", "countrycode"))
```

## 🔧 Running Locally

### Option 1: RStudio

1. Open `app.R` in RStudio
2. Click the **"Run App"** button
3. The app will open in your default browser at `http://localhost:8100`

### Option 2: R Console

```r
library(shiny)
runApp("app.R")
```

### Option 3: Terminal

```bash
Rscript -e "shiny::runApp('app.R', port=8080)"
```

## 📊 Data Sources

- **Death Rates:** `death_table.csv` - COVID-19 pandemic death rates by country (deaths per million)
- **Vaccination Data:** `vaccine_percent.csv` - COVID-19 vaccination percentages by location
- **Geographic Data:** Natural Earth via `rnaturalearth` R package for country boundaries and continent mapping

## 🎨 Design Features

- **Professional UI:** Blue and white color scheme with rounded boxes
- **Interactive Filtering:** Filter scatter plot data by continent
- **Dynamic Thresholds:** Adjustable mortality threshold slider for histogram visualization
- **Responsive Layout:** Dashboard adapts to different screen sizes
- **Data Visualization:** Multiple chart types (choropleth, scatter, boxplots, histograms)

## 🔄 Key Functions

### Data Loading

`load_data()` - Loads and merges COVID-19 death and vaccination data from CSV files, standardizes country names, and adds geographic/continental information using the `countrycode` package.

### Visualizations

- **Choropleth Map** - Global death rates with color gradient (light blue to dark red)
- **Scatter Plot** - Vaccination % vs. Deaths/million with regression line
- **Box Plots** - Distribution of vaccination rates and death rates by continent
- **Histogram** - Vaccination rates stratified by mortality level

## 🚢 Deployment

The app is deployed on **shinyapps.io**. To update the deployment:

```r
library(rsconnect)
deployApp()
```

## 📝 Notes

- Data is loaded once at startup for performance
- Missing values (NA) are handled gracefully in visualizations
- Country names are standardized (e.g., "United States" → "USA") for consistent merging
- Countries without continent information are filtered out

## 👤 Author

Devashree Pawar

## 📄 License

This project is created for educational purposes.

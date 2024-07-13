# Unicorn-Company-Analysis

### Overview :
This Python project, "Unicorn Companies Analysis," provides an in-depth examination of private companies with valuations exceeding $1 billion as of March 2022. The analysis covers various aspects, including company valuations, funding, country of origin, industry, select investors, and the timeline of their founding and achieving unicorn status. Below is a detailed description of the project's components and the insights derived from the analysis.

(This project is a part of Maven Analytics Challenge.)

### Recommended Analysis:
- Biggest Return on Investment (ROI): The project calculates and identifies which unicorn companies have provided the biggest returns on investment. This involves comparing the initial funding amounts to the current valuations.

- Time to Become a Unicorn: The analysis examines the average time it takes for companies to reach unicorn status from their founding year. It also investigates if the time required has changed over the years, reflecting shifts in market conditions and startup dynamics.

- Geographical Distribution of Unicorns: The project maps out the countries with the highest number of unicorns and identifies cities that serve as industry hubs. This geographic analysis reveals concentration areas and potential reasons behind these clusters.

- Top Investors: The analysis identifies which investors have funded the most unicorns, highlighting their influence and investment strategies in the startup ecosystem.

### Steps followed :
#### Data Loading and Pre-processing:
- Step 1: Import necessary libraries and load the dataset using Pandas.
- Step 2: Clean the data by changing datatypes, renaming columns and transforming values as per the requirement.
- Step 3: Update the dataframe once transformation is done.

#### Data Analysis:

- Create Visuals:
  
    a. Show basic summary -
    
        No of listed companies: 1073
        No of Industries: 15
        No of country
        No of cities
      
    b. Distribution of Companies per Industry -
    
        Pie chart
  
        industry_counts = df['Industry'].value_counts()
        fig = go.Figure(data=[go.Pie(labels=industry_counts.index, values=industry_counts.values)])
        
    c. Number of Companies per Industry -
    
        Bar chart
  
        industry_counts = df['Industry'].value_counts()
        fig = go.Figure(data=[go.Bar(x=industry_counts.index, y=industry_counts.values)])
        
    d. Count of Companies per Unicorn Label Year -
    
        Bar chart
        
        foundation_year_counts = df['UniYear'].value_counts().sort_index()
        fig = go.Figure(data=[go.Bar(x=foundation_year_counts.index, y=foundation_year_counts.values)])
        
    e. Top 10 Vehicles by Make -
    
        Stacked bar chart
        
        Y-axis = Make
        
        X-axis = Count of DOL Vehicle ID
        
        From Filters pane, Apply filter to 'Make' by selecting Filter Type Top N and set value as Count of DOL Vehicle ID.
        
    f. Vehicle by CAFV Eligibility -
    
        Pie chart
        
        Legend = CAFV Check
        
        Values = Count of CAFV Check
        
    g. Total Vehicle by State -
    
        Shape map
        
        Location = State
        
        Color Saturation = Count of DOL Vehicle ID
        
    h. Vehicle Type Distribution 1 -
    
        Donut chart
        
        Legend = Electric Type Vehicle Acronym
        
        Values = Count of Electric Type Vehicle Acronym
        (Emphasize BEV in this chart)
        
        Card
        
        Fields = BEV KPI
        
        Fields = BEV %age
        
    i. Vehicle Type Distribution 2 -
    
        Donut chart
        
        Legend = Electric Type Vehicle Acronym
        
        Values = Count of Electric Type Vehicle Acronym
        (Emphasize PHEV in this chart)
        
        Card
        
        Fields = PHEV KPI
        
        Fields = PHEV %age
        
    j. Filters -
    
        1. Electric Utility
        2. Make
        3. Model Year
        4. City

  
- Key Metrics and Visualizations:
  
  -The total number of electric vehicles (EVs) in the dataset, with a figure of 150.48K.
  
  -Average electric range of the vehicles is 67.88 kms.
  
  -BEVs (Battery Electric Vehicles): 117K, which is 77.6% of the total EVs.
   PHEVs (Plug-in Hybrid Electric Vehicles): 34K, which is 22.4% of the total EVs.
  
  -A line chart that shows the growth of EVs from 2010 onwards. The chart highlights significant growth over the years, peaking at 37K in 2023.
  
  -A treemap visualization showcasing the top 10 EV models by total number of vehicles. Notable models include:
  Model Y: 28.50K
  Model 3: 27.71K
  LEAF: 13.19K
  
  -A bar chart indicating the top vehicle manufacturers by the number of EVs. Tesla leads with 69K vehicles, followed by Nissan with 13K and Chevrolet with 12K.
  
  -A pie chart that classifies vehicles based on CAFV eligibility:
  Unknown (Battery not researched): 17.83K (11.85%)
  Eligible: 62.95K (41.83%)
  Not Eligible: 69.7K (46.32%)
  
  -A map of the United States highlighting the distribution of EVs across different states, providing a geographical perspective on EV adoption.


- Usage:
    This dashboard is designed for stakeholders and enthusiasts in the electric vehicle industry, including policymakers, manufacturers, and consumers. It can help identify trends, compare the performance of different EV models, and understand the impact of EVs in various regions.

- Dataset:
    https://mavenanalytics.io/data-playground?order=date_added%2Cdesc&search=unicorn

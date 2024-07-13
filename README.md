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
        
    e. Count of Companies per Foundation Year -
    
        Bar chart
        
        foundation_year_counts = df['FoundedOn'].value_counts().sort_index()
        fig = go.Figure(data=[go.Bar(x=foundation_year_counts.index, y=foundation_year_counts.values)])
        
    f. Number of Companies per Country -
    
        Line chart
        
        country_counts = df['Country'].value_counts().sort_index()
        fig = go.Figure(data=go.Scatter(x=country_counts.index, y=country_counts.values))
        
    g. Number of Companies per Continent -
    
        Line chart
        
        continent_counts = df['Continent'].value_counts().sort_index()
        fig = go.Figure(data=go.Scatter(x=continent_counts.index, y=continent_counts.values))
        
    h. Funding per Industry -
    
        Line chart
        
        industry_funding = df.groupby('Industry')['Funding(in $ Billions)'].sum().reset_index()
        fig.add_trace(go.Scatter(x=industry_funding['Industry'], y=industry_funding['Funding(in $ Billions)']))
        
    i. Valuation per Industry -
    
        Line chart
  
        industry_valuation = df.groupby('Industry')['Valuation(in $ Billions)'].sum().reset_index()
        fig.add_trace(go.Scatter(x=industry_valuation['Industry'], y=industry_valuation['Valuation(in $ Billions)']))
        
    j. Top-10 Investors by No. of Companies Invested in-
    
        investors_count = df_investors['Investors'].value_counts()
        top_10_investors = investors_count.head(10).reset_index()
        top_10_investors.columns = ['Investors', 'Frequency']
  
        fig = px.bar(top_10_investors, x='Investors', y='Frequency')

  
### Key Metrics and Insights:
  
    - Company Valuations and Funding: The dataset includes the current valuations of unicorn companies along with their total funding received. This information is crucial for understanding the financial health and market perception of these companies.

    - Country of Origin and Industry: The analysis identifies the country of origin for each unicorn and categorizes them into different industries. This helps in recognizing geographical and sector-specific trends in the unicorn landscape.

    - Investors: The project highlights key investors who have funded these unicorns, showcasing their role in the growth and success of these companies.

    - Timeline- Founding to Unicorn Status: For each company, the project records the year they were founded and the year they achieved unicorn status. This timeline provides insights into the speed of growth and market dynamics over time.


### Usage:
This project is designed for investors, entrepreneurs, and researchers interested in understanding the dynamics of unicorn companies. It offers valuable insights into investment returns, growth timelines, geographical trends, and key investors in the unicorn landscape.

### Dataset:
https://mavenanalytics.io/data-playground?order=date_added%2Cdesc&search=unicorn

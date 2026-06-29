# Demand Forecasting using Exponential Smoothing

## Project Overview
Accurate demand forecasting plays a critical role in inventory management, production planning, procurement, and supply chain decision-making. This project demonstrates how different Exponential Smoothing techniques can be selected and applied based on the underlying characteristics of historical demand data.
Using three monthly demand datasets spanning nine years, the project begins with exploratory data analysis to identify the presence of level, trend, and seasonality within each time series. Based on these observations, following forecasting models are implemented and evaluated:
- Simple Exponential Smoothing (SES)
- Holt's Trend Method
- Holt-Winters Exponential Smoothing

Rather than applying forecasting models indiscriminately, this project follows a structured analytical approach by first diagnosing the demand pattern, selecting an appropriate forecasting technique and validating the choice using forecast accuracy metrics such as Mean Absolute Error (MAE) and Mean Absolute Percentage Error (MAPE). The objective is to demonstrate not only how to build forecasting models, but also how to justify model selection using both visual analysis and quantitative evidence.

## Business Problem
  Accurate demand forecasting is one of the most important activities in supply chain planning, as it directly influences production, procurement, inventory management and customer service levels. Manufacturing companies must estimate future demand as accurately as possible to ensure that products are available when customers need them while avoiding unnecessary inventory costs.
  
  If a business consistently underestimates demand, it risks frequent stockouts, lost sales, delayed customer deliveries, and increased pressure on manufacturing and supply chain operations to replenish inventory within short timeframes. Conversely, consistently overestimating demand can result in excess inventory, higher warehousing costs, increased working capital tied up in stock and a greater risk of inventory obsolescence.
  
  This project demonstrates how historical demand data can be analysed to identify different demand patterns and how appropriate Exponential Smoothing techniques can be selected to generate accurate forecasts. The objective is not only to build forecasting models, but also to establish a systematic approach for selecting the most suitable forecasting method based on the characteristics of the data and validating that choice using quantitative performance metrics.

## Dataset Description
  The project uses three monthly demand datasets collected over a period of nine years. Each dataset represents the historical demand of a different product and exhibits distinct demand characteristics. The objective is to analyse these demand patterns before selecting an appropriate forecasting technique rather than assuming that a single forecasting model is suitable for every dataset.
  
  The datasets were intentionally analysed independently to demonstrate how different demand behaviours require different forecasting approaches. Throughout the project, exploratory data analysis was performed to identify the presence of level trend and seasonality before selecting forecasting models.

  The three datasets used in this project are:
- Premium Red - Monthly demand dataset used to study demand with relatively stable behaviour.
- Premium Blue - Monthly demand dataset exhibiting a combination of trend and seasonal patterns.
- Premium Plus Black - Monthly demand dataset containing a more complex demand pattern, requiring comparison of multiple Exponential Smoothing models before selecting the final forecasting approach.

Each dataset contains 108 monthly observations (9 years × 12 months), providing sufficient historical information for analysing long-term demand patterns and evaluating forecasting model performance.

## Methodology
  The forecasting process followed in this project emphasizes analytical decision-making rather than directly applying forecasting models. Instead of assuming that a single forecasting technique is suitable for every dataset, each product's historical demand was analysed independently before selecting an appropriate forecasting model.

  The methodology followed throughout the project is summarized below:
1.	Historical Demand Analysis:
    - Import and inspect monthly demand data.
    - Verify data quality and understand the forecasting horizon.
2.	Exploratory Data Analysis (EDA):
    - Visualize historical demand.
    - Identify the presence of level, trend and seasonality.
    - Examine overall demand behaviour using descriptive statistics.
3.	Model Selection:
    - Select the appropriate Exponential Smoothing technique based on the observed demand pattern.
    - Evaluate whether additive or multiplicative seasonality is more appropriate where applicable.
5.	Model Development:
    - Build forecasting models using Simple Exponential Smoothing (SES), Holt's Trend Method and Holt-Winters Exponential Smoothing.
    - Estimate optimal smoothing parameters using model optimization.
6.	Model Evaluation:
    - Compare forecasting performance using Mean Absolute Error (MAE) and Mean Absolute Percentage Error (MAPE).
    - Validate model assumptions using both graphical analysis and quantitative performance metrics.
7.	Model Comparison and Interpretation:
    - Compare competing forecasting models.
    - Select the final forecasting model based on forecasting accuracy and the underlying demand characteristics.
    - Interpret the results from a business and supply chain planning perspective.

## Forecasting Model Selection Summary
  Each dataset was analyzed independently to identify its underlying demand characteristics before selecting an appropriate forecasting technique. Rather than assuming a single forecasting model would perform well across all products, multiple Exponential Smoothing methods were evaluated and compared using Mean Absolute Error (MAE) and Mean Absolute Percentage Error (MAPE). The final model for each dataset was selected based on both the observed demand pattern and quantitative forecasting accuracy.

![Forecasting_model_selection_summary](images/Forecasting_model_selection_summary.png)

  The results demonstrate that forecasting accuracy depends on selecting a model that aligns with the underlying characteristics of the demand data rather than consistently applying the most complex forecasting technique. Simpler models such as SES may outperform more sophisticated approaches when the demand pattern is relatively stable, whereas datasets exhibiting trend and seasonality benefit from Holt-Winters Exponential Smoothing.

## Key Learnings
  This project provided several practical insights into demand forecasting and model selection using Exponential Smoothing techniques:
- Visual inspection alone is not sufficient for identifying demand patterns. Although demand plots provide an initial understanding of the data, statistical analysis and quantitative validation are necessary to confirm the presence of trend and seasonality before selecting a forecasting model.
- The smoothing parameters (α, β and γ) are learning parameters rather than direct indicators of level, trend or seasonality. Their optimized values determine how quickly the forecasting model updates its estimates in response to new observations and should always be interpreted in the context of the underlying data.
- A more complex forecasting model does not necessarily produce better forecasts. Adding trend or seasonal components does not guarantee improved forecasting accuracy. Model selection should always be based on the characteristics of the dataset and validated using objective performance metrics.
- Forecast accuracy metrics are essential for model evaluation. Mean Absolute Error (MAE) and Mean Absolute Percentage Error (MAPE) provided an objective basis for comparing competing forecasting models and selecting the final model rather than relying solely on visual interpretation.
- Forecasting is an analytical decision-making process rather than simply applying algorithms. The project emphasized a structured workflow consisting of exploratory data analysis, pattern identification, model selection, performance evaluation and business interpretation to arrive at the most appropriate forecasting solution.

## Repository Structure

```text
Demand-Forecasting-Using-Exponential-Smoothing/
│
├── README.md                         # Project documentation
├── requirements.txt                  # Python dependencies
│
├── data/
│   └── Bosch_Demand_Data.xlsx        # Excel workbook containing all three datasets
│
├── notebooks/
│   ├── Basic_Plus_Red_SES.ipynb
│   ├── Premium_Blue_Holt-Winters_Additive.ipynb
│   └── Premium_Black_Holt-Winters_Multiplicative.ipynb
│
└── images/
    ├── Methodology_workflow.png
    ├── Forecasting_model_selection_summary.png
    ├── Demand_pattern_comparison.png
    └── Selected_model_performance.png
```

## Future Improvements
  While the forecasting models developed in this project produced accurate results for the available datasets, several enhancements could further improve forecasting performance and extend the scope of the analysis:
- Longer Historical Data: Incorporating additional years of historical demand would provide more information for estimating long-term demand patterns and optimizing model parameters.
- Incorporating External Factors: The models used in this project rely solely on historical demand. Future work could incorporate external variables such as promotions, holidays, pricing changes, macroeconomic indicators, or competitor activities by using forecasting techniques capable of handling exogenous variables.
- Comparison with Advanced Forecasting Models: The analysis can be extended by comparing Exponential Smoothing techniques with more advanced forecasting approaches such as ARIMA, SARIMA, Prophet, or machine learning models to evaluate forecasting performance under different demand patterns.
- Forecasting Longer Time Horizons: The project currently focuses on model development and evaluation using historical data. Future work could investigate multi-period forecasting performance and compare model accuracy over different forecasting horizons.
- Business Integration: The forecasting models can be integrated into inventory planning and production scheduling workflows to support operational decision-making and improve supply chain performance.

  







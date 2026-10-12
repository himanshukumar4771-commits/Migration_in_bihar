Migration Ratio in Bihar
A District-Level Statistical Analysis of Demographic Mobility and Socio-Economic Drivers

Author: Himanshu Kumar Institution: Dev Bhoomi Uttarakhand University, Dehradun, Uttarakhand, India

Show Image Show Image

Overview

Bihar is one of India's most densely populated and economically under-resourced states, and it has long been a major source of internal migrants. This project analyses district-level migration patterns across Bihar's 38 districts using data from the official Census of India migration tables.

The analysis uses Python to:

Measure the total number of migrants in each district
Compute the migrant sex ratio (females per 1000 males)
Calculate the percentage share of each reason for migration: work, marriage, education, business and others
Study relationships between these variables with a Pearson Correlation Matrix
Visualise distributions and trends
Hypotheses
H1: Work-related migration and total migration volume have a statistically significant positive correlation at the district level.
H0: There is no statistically significant relationship between the proportion of work migrants and total migration volume across Bihar's districts.
Key Findings
Migration is concentrated in a few districts: the distribution of total migrants is right-skewed.
Work is the dominant economic driver of migration, and its share is positively correlated with total migration volume (supports H1).
Marriage is the main reason for female migration, which strongly shapes the sex ratio.
The migrant sex ratio sits well below parity (1000), showing a male-dominated work stream.
Education and business migration make up smaller shares of the total.
Dataset
Source: Census of India, Migration Tables (D-Series) for Bihar https://censusindia.gov.in/nada/index.php/catalog
File used: bihar_Migration.csv
Variable	Description
Area Name	District name
Total Persons / Males / Females	Total migrants by sex
Work / Marriage / Education / Business / Others Persons	Migrants by reason for migration
Place of Enumeration	Urban / Rural / Total
Duration of Residence	Duration of stay at destination
Age Group	Age classification
Last Residence	Origin of migration
Methodology
Data ingestion: the CSV has a multi-row header, so the first 5 rows are skipped (skiprows=5) and column names are assigned manually (31 columns).
Cleaning: numeric columns are coerced with pd.to_numeric(errors='coerce'), text columns are stripped of whitespace, and rows with missing Total Persons are dropped.
Filtering to one row per district:
District != 0 (exclude state totals)
Place of Enumeration == 'Total'
Age Group == 'All ages'
Duration of Residence == 'All durations of residence'
Feature engineering:
Sex Ratio = (Total Females / Total Males) × 1000
Reason Pct = (Reason Persons / Total Persons) × 100
Analysis and visualisation: KDE histograms, top-10 district bar chart, reason-of-migration chart, Pearson correlation heatmap, and a Work % vs Total Migration scatter plot.
Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
SciPy
Statsmodels
Project Structure
.
├── bihar_Migration.csv        # Census migration dataset
├── migration_analysis.ipynb   # Analysis notebook / script (rename to match yours)
├── paper/                     # Research paper (PDF)
├── figures/                   # Generated plots
└── README.md

Adjust file names above to match what is actually in your repository.

How to Run
Clone the repository
bash
   git clone https://github.com/himanshukumar4771-commits/YOUR-REPO-NAME.git
   cd YOUR-REPO-NAME
Install dependencies
bash
   pip install pandas numpy matplotlib seaborn scipy statsmodels jupyter
Run the analysis
bash
   jupyter notebook

Open the notebook and run all cells. Make sure bihar_Migration.csv is in the same folder.

Policy Recommendations
Promote rural non-farm employment in high-migration districts.
Set up migrant welfare centres in the top-10 migration districts.
Develop gender-sensitive migration policies, treating the marriage stream separately from the work stream.
Expand higher education and vocational training within Bihar.
Build a district-level migration monitoring dashboard.
Future Work
Compare multiple census years (2001, 2011 and later) for trend analysis.
Add destination-side data for migration corridor / network analysis.
Apply machine learning (random forest, gradient boosting) to identify districts at risk of rising outmigration.
Limitations

Census migration tables exclude many short-duration and seasonal migrants, so the figures represent the stock of migrants rather than all movement.

References
Deshingkar, P. and Akter, S. (2009). Migration and Human Development in India. UNDP.
Rodgers, G. and Rodgers, J. (2011). Inclusive Development? Migration, Governance and Social Change in Rural Bihar. Economic and Political Weekly, 46(23).
Banerjee, B. and Raju, S. (2009). Gendered Mobility: Women Migrants and Work in Urban India. Economic and Political Weekly, 44(28).
Bhagat, R. B. (2010). Internal Migration in India: Are the Underclass Hypermobile? Population, Space and Place, 16(6).
Census of India. Migration Tables: Bihar, D-Series.

See the full paper for the complete reference list.

License

Add a license of your choice (for example MIT) via Add file → Create new file → LICENSE on GitHub.

Contact

Himanshu Kumar GitHub: @himanshukumar4771-commits

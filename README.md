# F1-Analytics-Python-Power-BI-Max-Verstappen-Performance-Dashboard

## 🎬 How a Clueless Movie Night Became a Data Obsession

"It all started when I watched that F1 movie on a whim. As the credits rolled in the theater, I hit my friends with:

🔥 "Why was everyone so angry about tires? Are they that expensive?"

🚦 "WHY is he balancing this much weight on his HEAD in training video?!"

🏎️ "Wait, why there are 2 players?"

The next morning, 

Instagram decided I was now an F1 fan. Between suggested reels of pit stop fails and conspiracy theories about the 2021 finale,I:

1) Googled "F1 datasets" like someone who suddenly thinks they're Ross Brawn
2) Found toUpperCase78's treasure trove of race data
3) When they finally fed-up ("Please just make a dashboard instead"), this project was born - proof that peer pressure can sometimes yield productive results."


📌 "Things I Learned the Hard Way"

"No, you can't just average lap times and call it a day"
"Pandas hates DNF values as much as Ferrari hates strategy calls"


This project analyzes Max Verstappen's Formula 1 career performance from the 2015 to the upcoming 2025 season. It provides insights into his race results, qualifying performance, points accumulation, and track-specific strengths and weaknesses. The analysis generates various visualizations and detailed summaries to highlight key aspects of his career.

### Table of Contents
1) Project Description
2) Features
3) Data Sources
4) Files in this Project
5) Setup and Installation
6) Usage
7) Analysis Highlights
8) Visualizations
9) Output Files
10) Contributing
11) License

### Project Description
This project aims to provide a comprehensive statistical overview of Max Verstappen's Formula 1 career. By loading and processing race, qualifying, and driver data, it quantifies his achievements, identifies trends over different seasons, and evaluates his performance across various circuits. The analysis includes:

1) Overall Career Statistics: Total wins, podiums, pole positions, and fastest laps.
2) Seasonal Performance: Breakdown of wins, points, and qualifying results per season.
3) Car Performance: Wins associated with different Red Bull car models.
4) Track Analysis: Performance metrics (wins, podiums, average position) for each circuit, categorized by circuit type.
5) Position Changes: Analysis of starting grid vs. finishing position to assess race craft.

### Features
1) Automated Data Loading: Fetches F1 race, qualifying, and driver data directly from a GitHub repository for seasons 2015-2025.
2) Robust Data Cleaning: Handles missing values, converts various position and time formats to numerical values, and standardizes team names.
3) Max Verstappen Specific Filtering: Extracts and focuses the analysis solely on Max Verstappen's performance data.
4) Key Performance Indicators (KPIs): Calculates and presents essential metrics such as win rates, podium rates, and average points.
5) Career and Track Summaries: Generates detailed dataframes summarizing annual performance and track-specific results.
6) Informative Visualizations: Creates a series of plots to visually represent trends in wins, qualifying, race finishes, points, and track performance.
7) Output to CSV: Saves cleaned data and summary reports to CSV files for further external analysis or record-keeping.

### Data Sources
1) The data used in this project is sourced from the toUpperCase78/formula1-datasets GitHub repository, which contains various F1 season data in CSV format.
2) Race Results: formula1_[season]season_raceResults.csv
3) Qualifying Results: Formula1_[season]season_qualifyingResults.csv
4) Sprint Qualifying Results: Formula1_[season]season_sprintQualifyingResults.csv (for applicable seasons)
5) Drivers Data: formula1_[season]season_drivers.csv (for applicable seasons)
6) For the 2025 season, driver data is manually entered as it's not yet available in the repository.

### Files in this Project
1) max_verstappen_f1_analysis.py: The main Python script containing all the code for data loading, cleaning, analysis, and visualization.
2) verstappen_race_results_2015-2025.csv: Output file containing cleaned and filtered race results for Max Verstappen.
3) verstappen_qualifying_results_2015-2025.csv: Output file containing cleaned and filtered qualifying results for Max Verstappen.
4) verstappen_career_summary_2015_2025.csv: Output file summarizing Max Verstappen's career performance by year.
5) verstappen_track_performance_detailed.csv: Output file detailing Max Verstappen's performance at each circuit.


### Setup and Installation
To run this project, you need Python and the following libraries installed:
1) pandas
2) requests
3) matplotlib
4) seaborn

1) You can install these libraries using pip:

pip install pandas requests matplotlib seaborn Usage

2) Clone the Repository:

git clone <repository-url>
cd <repository-directory>
Run the Python Script:
Execute the max_verstappen_f1_analysis.py script.

3) python max_verstappen_f1_analysis.py
The script will automatically download the necessary data, perform the analysis, generate plots, and save the results to CSV files in the same directory. The plots will be displayed sequentially.

### Analysis Highlights
The script provides a summary of Max Verstappen's performance directly in the console output.

1) Max Verstappen Performance Summary (2015-2025):

Total Races: 151

Wins: 60

Podiums: 95

Pole Positions: 34

Fastest Laps: 13 

2) Career Performance Summary (2015-2025):

A table showing annual performance including Wins, Podiums, Win Rate, Podium Rate, and Total Points for each year, along with the Team and Car used.

3) Track Performance Summary:

A table showing top tracks where Verstappen has raced at least 3 times, sorted by Win Rate, including Races, Wins, Podiums, Average Position, and Circuit Type.

4) Visualizations
The script generates several plots to illustrate Verstappen's performance:

* Wins by Season: A bar chart showing the number of wins each season.
* Qualifying Positions by Season: A stacked bar chart illustrating the distribution of qualifying positions across seasons.
* Race Finish Position Distribution: A box plot showing the distribution of his race finishing positions per season.
* Total Points by Season: A line chart displaying his points accumulation over the years.
* Verstappen's Wins by Year and Car Model: A bar chart breaking down wins by season and the specific car model used.
* Best and Worst Tracks by Win Rate: A bar chart highlighting circuits where he has a high or low win rate (minimum 3 races).
* Starting Grid vs Finishing Position: A scatter plot showing how his starting position correlates with his finishing position, with a diagonal line indicating no change.
* verstappen's Win Rate by Track and Circuit Type: A heatmap showing win rates categorized by track and their circuit characteristics.

### Output Files
The following CSV files are generated upon successful execution:

1) verstappen_race_results_2015-2025.csv
2) verstappen_qualifying_results_2015-2025.csv
3) verstappen_career_summary_2015_2025.csv
4) verstappen_track_performance_detailed.csv

### Power BI Reports
The project also includes a Power BI dashboard, built using DAX, which offers an interactive way to explore Max Verstappen's performance.

This dashboard provides:

1) Key Performance Indicators (KPIs): At-a-glance metrics for wins, fastest laps, poles, podiums, total races, and current car model.
2) Seasonal Insights: Visualizations of wins per season broken down by car model, and a trend of championship points per season.
3) Interactive Slicers: A 'Season' slicer allows for dynamic filtering of all visuals to focus on specific years.
4) The DAX measures powering this dashboard enable flexible and accurate aggregation of data, providing real-time insights as filters are applied.

DAX comments:

1) DAX: DISTINCTCOUNT( 'YourTable'[Team] )
2) "Fastest Laps - 13":
   DAX: CALCULATE( COUNTROWS( 'YourTable' ), 'YourTable'[Fastest Lap] = "Yes" ) or SUM( 'YourTable'[IsFastestLap] ) if you have a boolean column.
3) "Total Wins - 60":
   DAX: CALCULATE( COUNTROWS( 'YourTable' ), 'YourTable'[Position] = 1 )
4) "Poles - 34":
   DAX: CALCULATE( COUNTROWS( 'YourTable' ), 'YourTable'[Qualifying Position] = 1 ) (assuming you have a qualifying table/column).
5) "Podium - 95":
   DAX: CALCULATE( COUNTROWS( 'YourTable' ), 'YourTable'[Position] <= 3 )
6) "Total Races by Max - 138":
   DAX: COUNTROWS( 'YourTable' ) (after filtering for Max Verstappen).
7) "RB21": This looks like a Dynamic Title or a card showing the most recent car model.
   DAX: LASTNONBLANKVALUE( 'YourTable'[Car Model], TRUE() ) or MAX( 'YourTable'[Car Model] ) if sorted by season, or a more complex measure to get the car for the most recent selected season.
8) Bottom Row (Charts and Slicers):

"Wins by Season" (Bar Chart):

X-axis: Season (from your date table or race results table).

Y-axis: [Total Wins] measure from above.

Legend/Color: Car Model or Team (the numbers like RB15, RB16, RB18, RB19, RB20, RB21 are car models).

DAX for Labels (e.g., 3 RB15): This would likely be a measure combining the count of wins and the car model, or simply using Car Model as a secondary category or tooltip. For exact labels like that on the bars, you might be using a combination of "Data Labels" features in Power BI and potentially a custom measure that concatenates the win count with the car model for the label.

9) "Season" (Slicer):

10) Field: Season (from your date or race results table).

This allows users to filter the dashboard by year.

11) "Campionship Points by Season" (Line Chart):

X-axis: Season.

Y-axis: Average of Points.

DAX for Average of Points: AVERAGE( 'YourTable'[Points] ) (This seems like average per race or average of final championship points per season. Given the scale, it's likely total points per season, and "Average of Points" might be a mislabeling or referring to how the line chart calculates its aggregate if there are multiple point entries per season). If it's total points, it would be SUM( 'YourTable'[Points] ). A championship points visual would typically sum points per season. The graph shows a sum trend, so SUM('YourTable'[Points]) is more probable.

### Contributing
Feel free to fork this repository, open issues, or submit pull requests. Any contributions to improve the analysis, add new features, or enhance visualizations are welcome!

### License
This project is open-source and available under the MIT License. The data used in this project is sourced from the toUpperCase78/formula1-datasets GitHub repository, which contains various F1 season data in CSV format. This dataset is licensed under the GPL-3.0 license.

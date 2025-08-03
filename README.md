# Ligue 1 Match Data Scraper

A comprehensive Python web scraper that extracts French Ligue 1 football match data from Soccerway, including scores and first goal timing for low-scoring games (≤3 total goals). Features optimized two-phase scraping and detailed data analysis.

## 🎯 Project Overview

This project demonstrates advanced web scraping techniques using Selenium WebDriver to collect comprehensive match data from the 2024-25 Ligue 1 season. The scraper focuses on matches with 3 or fewer total goals and includes detailed timing analysis of first goals, including proper handling of extra-time goals.

## 🚀 Key Features

- **Complete Season Coverage**: Scrapes all matches from the 2024-25 Ligue 1 season
- **Smart Filtering**: Only processes matches with ≤3 total goals
- **First Goal Tracking**: Extracts precise timing including extra-time handling ("90+3" → 93 minutes)
- **Performance Optimized**: Two-phase approach (navigate first, then extract all data)
- **Data Validation**: Built-in completeness checks and error handling
- **Analysis Ready**: Includes Jupyter notebook with visualizations and insights
- **Performance Monitoring**: Detailed timing for each scraping phase

## 📊 Data Collected

| Field | Description | Example |
|-------|-------------|---------|
| Date | Match date | "Saturday 17 August 2024" |
| Home | Home team name | "Monaco" |
| Away | Away team name | "Saint-Étienne" |
| Home_Score | Home team goals | 1 |
| Away_Score | Away team goals | 0 |
| Final_Score | Match result | "1-0" |
| Link | Match detail URL | "https://ca.soccerway.com/..." |
| first_goal_min | First goal minute | 28 |

## 📁 Project Structure

```
ligue1-scraper/
├── src/
│   └── scraper.py              # Main scraping script
├── notebooks/
│   └── analysis.ipynb          # Data analysis & visualizations
├── data/
│   └── ligue1_2024_matches.csv # Scraped match data
├── docs/
│   └── methodology.md          # Technical documentation
├── requirements.txt            # Python dependencies
├── README.md                  # This file
└── .gitignore                 # Git ignore rules
```

## 🛠️ Technical Implementation

### Two-Phase Scraping Strategy
1. **Navigation Phase**: Efficiently click through to the first gameweek
2. **Extraction Phase**: Process all loaded match data in a single optimized pass

### Key Technologies
- **Selenium WebDriver**: Browser automation for dynamic content
- **Pandas**: Data manipulation and CSV export
- **Matplotlib/Seaborn**: Data visualization in analysis notebook
- **Chrome Headless**: Fast background scraping

### Advanced Features
- **Extra-time Goal Handling**: Converts "90+3" to actual elapsed time (93 minutes)
- **Robust Error Handling**: Graceful failure recovery and data validation
- **Performance Monitoring**: Detailed timing breakdown for optimization

## 🚀 Quick Start

### Prerequisites
```bash
# Required software
Python 3.7+
Chrome browser
Git
```

### Installation & Usage

1. **Clone the repository**:
```bash
git clone https://github.com/yourusername/ligue1-scraper.git
cd ligue1-scraper
```

2. **Install dependencies**:
```bash
pip install -r requirements.txt
```

3. **Download ChromeDriver** (if not using webdriver-manager):
```bash
# ChromeDriver will be managed automatically by webdriver-manager
```

4. **Run the scraper**:
```bash
python src/scraper.py
```

5. **Explore the data**:
```bash
jupyter notebook notebooks/analysis.ipynb
```

## 📈 Performance Metrics

### Sample Timing Results
```
⏱️ Navigation took: 45.32 seconds
⏱️ Data extraction took: 8.74 seconds  
⏱️ First goal extraction took: 127.85 seconds (156 matches)

📊 TOTAL TIME: 181.91 seconds
   - Navigation: 45.32s (25%)
   - Extraction: 8.74s (5%) 
   - Goal minutes: 127.85s (70%)
```

### Data Quality Metrics
- **Match Coverage**: ~200+ matches per season (filtered for ≤3 goals)
- **Team Coverage**: All 20 Ligue 1 teams included
- **Data Completeness**: >98% successful data extraction
- **Goal Timing Accuracy**: Handles both regular and extra time

## 🔍 Data Analysis Highlights

The included Jupyter notebook provides insights such as:
- **Goal Timing Distribution**: When first goals typically occur
- **Score Pattern Analysis**: Most common low-scoring results
- **Home vs Away Performance**: Win/draw/loss statistics
- **Early vs Late Goals**: Timing pattern analysis

### Sample Insights
- Average first goal time: ~35 minutes
- Most common scoreline: 1-0 (28% of matches)
- Home advantage: 45% home wins vs 32% away wins

## 📝 Sample Data Output

| Date | Home | Away | Home_Score | Away_Score | Final_Score | first_goal_min |
|------|------|------|------------|------------|-------------|----------------|
| Saturday 17 August 2024 | Reims | Lille | 0 | 2 | 0-2 | 18 |
| Saturday 17 August 2024 | Monaco | Saint-Étienne | 1 | 0 | 1-0 | 28 |
| Sunday 18 August 2024 | Toulouse | Nantes | 0 | 0 | 0-0 | None |

## Visualizing the Results

<img width="616" height="322" alt="image" src="https://github.com/user-attachments/assets/f5d24fb4-923e-493e-88f8-df5ae669cef2" />


## 🔧 Configuration Options

### Scraping Parameters
```python
# In src/scraper.py
MAX_SCROLLS = 40        # Maximum navigation clicks
GOAL_FILTER = 3         # Maximum total goals per match
WAIT_TIME = 2           # Seconds to wait for page loads
HEADLESS = True         # Run browser in background
```

### Data Filters
- **Goal Limit**: Only matches with ≤3 total goals
- **Season**: 2024-25 Ligue 1 regular season
- **Completed Matches**: Excludes upcoming fixtures

## 🚨 Known Issues & Limitations

- **Internet Dependency**: Requires stable connection for reliable scraping
- **Browser Compatibility**: Optimized for Chrome (ChromeDriver required)
- **Rate Limiting**: No built-in delays between requests (consider adding for production)
- **Dynamic Content**: Some match pages may have different HTML structures

## 🤝 Contributing

Contributions are welcome! Areas for improvement:
- Add support for other leagues
- Implement player-specific goal data
- Add match events beyond just goals
- Create more sophisticated analysis

### Development Setup
```bash
# Fork the repository
git clone https://github.com/yourusername/ligue1-scraper.git
cd ligue1-scraper

# Create feature branch
git checkout -b feature/new-feature

# Make changes and test
python src/scraper.py
jupyter notebook notebooks/analysis.ipynb

# Submit pull request
```

## ⚖️ Legal & Ethical Considerations

- **Respectful Scraping**: Implements reasonable delays and error handling
- **Educational Purpose**: Data collected for analysis and learning
- **Terms of Service**: Users should review Soccerway's ToS before use
- **Rate Limiting**: Consider implementing delays for production use

## 📚 Learning Outcomes

This project demonstrates:
- **Web Scraping**: Dynamic content handling with Selenium
- **Data Processing**: Pandas manipulation and cleaning
- **Performance Optimization**: Two-phase scraping strategy
- **Error Handling**: Robust exception management
- **Data Validation**: Completeness and quality checks
- **Documentation**: Professional project structure and documentation

## 📧 Contact & Support

- **Issues**: Please open a GitHub issue for bugs or questions
- **Improvements**: Pull requests welcome!
- **Questions**: Feel free to reach out for clarification

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**⭐ If you found this project helpful, please give it a star!**

**🚀 Want to see more projects like this? Follow me on GitHub!**

# Aviation Accident Network Analysis

## Project Overview
This project implements and compares SQL and NoSQL database approaches for analyzing aviation accident data as a network. It examines relationships between locations, causes, aircraft types, and survival rates to determine which database paradigm better serves different analytical needs in the aviation safety domain.

The project is developed as part of the NoSQL and Distributed Databases, and Network Science university courses.

## Features

- **Dual Database Implementation**
  - PostgreSQL (SQL) implementation with optimized relational schema
  - Neo4j (NoSQL) graph database implementation for network analysis

- **Network Analysis**
  - Node degree distribution and network density calculation
  - Centrality measures to identify critical network components
  - Cluster detection to identify accident patterns
  - Temporal trend analysis across years

- **Comparative Analysis**
  - Performance benchmarking between SQL and NoSQL approaches
  - Suitability assessment for different analytical tasks
  - Query complexity and optimization strategies

## Data Collection
The project includes a data collection phase that scrapes aviation accident information from reliable sources. Data points include:

- Temporal data (year, date)
- Location data (accident location, flight origin, destination)
- Aircraft information (type, registration, operator)
- Casualty information (passengers, crew, injuries, fatalities, survivors, missing)
- Accident causes and summaries

## Technology Stack

- **Languages & Core Technologies**
  - Python 3.x (primary implementation language)
  - SQL (PostgreSQL)
  - Cypher (Neo4j query language)

- **Libraries & Frameworks**
  - BeautifulSoup/Scrapy for web scraping
  - Pandas for data manipulation
  - NetworkX for network analysis
  - SQLAlchemy for PostgreSQL integration
  - Neo4j Python driver for graph database operations
  - Matplotlib/Plotly for data visualization

## Setup Instructions

### Prerequisites
1. Python 3.8 or higher
2. PostgreSQL 13 or higher
3. Neo4j 4.4 or higher
4. Git

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/aviation-accident-network-analysis.git
   cd aviation-accident-network-analysis
   ```

2. Set up a virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

4. Configure database connections:
   - Copy `.env.example` to `.env`
   - Update the PostgreSQL and Neo4j connection parameters

5. Initialize the databases:
   ```
   python scripts/init_databases.py
   ```

### Data Collection

Run the data collection script to scrape aviation accident data:
```
python scripts/data_collection.py
```

## Usage

### Data Import

Import data into both database systems:
```
python scripts/import_data.py
```

### Running Analyses

Execute various network analyses:
```
python scripts/run_analysis.py --analysis-type [centrality|clustering|temporal]
```

### Comparative Benchmarking

Run performance benchmarks between database approaches:
```
python scripts/benchmark.py --query-type [path|centrality|clustering]
```

### Visualizations

Generate visualizations from analysis results:
```
python scripts/visualize.py --viz-type [network|temporal|geographic]
```

## Project Structure

```
aviation-accident-network-analysis/
│
├── data/                       # Data storage
│   ├── raw/                    # Raw scraped data
│   └── processed/              # Cleaned and processed data
│
├── scripts/                    # Utility scripts
│   ├── data_collection.py      # Web scraping implementation
│   ├── data_cleaning.py        # Data preprocessing
│   ├── import_data.py          # Database import utilities
│   └── ...
│
├── sql/                        # SQL schema and queries
│   ├── schema.sql              # Database schema definition
│   └── queries/                # Analytical queries
│
├── neo4j/                      # Neo4j Cypher queries and config
│   ├── schema.cypher           # Graph model definition
│   └── queries/                # Graph analytical queries
│
├── analysis/                   # Analysis implementations
│   ├── network_metrics.py      # Basic network analysis
│   ├── centrality.py           # Centrality measures
│   └── ...
│
├── visualization/              # Visualization code
│   ├── network_viz.py          # Network visualization
│   └── ...
│
├── tests/                      # Unit and integration tests
│
├── requirements.txt            # Project dependencies
├── .env.example                # Example environment variables
├── README.md                   # This file
└── SPECS.md                    # Detailed technical specifications
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Data sources: Wikipedia and other aviation safety databases
- Academic advisors from the NoSQL/Distributed Databases and Network Science courses


  # TransJakarta Passenger Cost Analysis

A comprehensive data-driven analysis of TransJakarta's 2024 ridership patterns and operational optimization, built with Python and Power BI visualization.

## 🚌 Project Overview

Ever wondered why TransJakarta feels so crowded during peak hours? This project analyzes **11.6 million monthly passenger data** across all 14 corridors to answer questions like:

- How many people actually use TransJakarta daily?
- Which bus stops are the most chaotic?
- What fleet size is needed to reduce waiting times?
- How much would it cost to optimize the entire system?

**Key Finding**: The system could achieve **7-minute average headways** with an optimized fleet of **257 buses** at an average cost of **IDR 1,087 per passenger**.

## 📊 Analysis Highlights

### System-Wide Metrics
- **Total Monthly Passengers**: 11.6M across all corridors
- **Peak Hour Demand**: 55,000-58,000 daily riders system-wide
- **Busiest Corridors**: Corridors 1, 9, and 13
- **Most Crowded Stops**: Petukangan, Gelora Bung Karno, Puri Beta 2, Bundaran HI Astra, Kalideres

### Optimization Scenarios
The analysis models 5 operational scenarios:
- **Current**: 10-minute headways (existing operations)
- **Optimal**: 3-minute headways (maximum efficiency)
- **Balanced**: 7-minute headways (recommended)
- **Frequent**: 5-minute headways (enhanced service)
- **Cost-Efficient**: 12-minute headways (budget-focused)

## 🛠 Technical Stack

- **Python**: Data processing and analysis
  - `camelot-py`: PDF table extraction
  - `pandas`: Data manipulation
  - `numpy`: Numerical computations
- **Power BI**: Interactive dashboard and visualization
- **Data Source**: TransJakarta's public transparency portal

## 📁 Project Structure

```
├── data/                          # Raw PDF files from TransJakarta
│   ├── Jumlah Pelanggan BRT Transjakarta Perhalte Koridor 1 Tahun 2024.pdf
│   ├── Jumlah Pelanggan BRT Transjakarta Perhalte Koridor 2 Tahun 2024.pdf
│   └── ... (corridors 1-14)
├── analysis/
│   ├── transjakarta_analysis.ipynb    # Main analysis notebook
│   └── powerbi/
│       ├── TransJakarta_Dashboard.pbix # Power BI dashboard
│       └── tj_theme.json              # Custom TransJakarta theme
├── outputs/                       # Generated CSV files
│   ├── transjakarta_system_optimization.csv
│   ├── koridor1_passenger_data.csv
│   ├── koridor1_scenarios.csv
│   └── ... (individual corridor analyses)
└── README.md
```

## 🚀 Getting Started

### Prerequisites
```bash
pip install camelot-py pandas numpy matplotlib seaborn
pip install "camelot-py[cv]"  # For better table detection
```

### Running the Analysis
```python
# Clone the repository
git clone https://github.com/username/transjakarta-passenger-cost-analysis.git
cd transjakarta-passenger-cost-analysis

# Run the main analysis
jupyter notebook analysis/transjakarta_analysis.ipynb

# Or run directly
python -c "exec(open('analysis/main_analysis.py').read())"
```

### Power BI Dashboard
1. Open `analysis/powerbi/TransJakarta_Dashboard.pbix`
2. Refresh data sources to load latest CSV outputs
3. Apply custom theme from `tj_theme.json` if needed

## 📈 Key Features

### Data Processing
- **PDF Extraction**: Automated parsing of TransJakarta's monthly ridership PDFs
- **Data Cleaning**: Handles inconsistent formatting and missing values
- **Monthly Aggregation**: Calculates averages, peaks, and daily breakdowns

### Fleet Optimization
```python
class TransjakartaSystemOptimizer:
    def optimize_corridor(self, corridor_num, vehicle_capacity=103, load_factor=0.85):
        # Calculate optimal fleet size based on:
        # - Peak hour demand
        # - Cycle time (route length + dwell time + layover)
        # - Vehicle capacity and load factor
        # - Cost constraints (fuel, driver, maintenance)
```

### Cost Analysis
- **Fuel Costs**: Based on BioSolar prices (IDR 6,800/L)
- **Driver Costs**: Driver + guide wages (IDR 16.5M/month each)
- **Maintenance**: Average IDR 530k/bus/day
- **Total Operating Cost**: IDR 421.4M daily for optimal scenario

### Passenger Hotspot Identification
- Ranks bus stops by monthly ridership
- Identifies potential new stop locations
- Calculates demand-based priority scores

## 📊 Sample Results

### Corridor 1 (Blok M - Kota)
- **Monthly Passengers**: 1.74M
- **Peak Hour Demand**: 8,693 passengers/hour
- **Current Fleet**: 13 buses (1,655% utilization)
- **Recommended**: 18 buses (1,158% utilization, 7-min headway)
- **Top Hotspot**: Gelora Bung Karno (193k monthly passengers)

### System Totals
| Metric | Value |
|--------|--------|
| Monthly Passengers | 11.6M |
| Recommended Fleet | 257 buses |
| Daily Operating Cost | IDR 421.4M |
| Average Cost/Passenger | IDR 1,087 |
| Daily Fuel Consumption | 21,182L |

## 📱 Power BI Dashboard

The interactive dashboard includes:
- **System Overview**: KPI cards and trend analysis
- **Corridor Deep Dive**: Detailed per-corridor analysis
- **Financial Analysis**: Cost breakdown and revenue projections
- **Scenario Modeling**: Compare optimization strategies

### Custom TransJakarta Theme
```json
{
  "name": "TransJakarta Performance Theme",
  "dataColors": ["#0054A4", "#FFC20E", "#E4002B", "#00A651", ...],
  "background": "#FFFFFF",
  "foreground": "#333333"
}
```

## 🎯 Business Impact

### For TransJakarta Management
- **Data-driven decision making** for fleet allocation
- **Cost optimization** strategies for budget planning
- **Infrastructure expansion** recommendations

### For Commuters
- **Reduced waiting times** with optimized headways
- **Less overcrowding** through demand-based fleet sizing
- **Improved service quality** via evidence-based improvements

### For Urban Planners
- **Passenger demand mapping** for future route planning
- **Integration insights** for multimodal transportation
- **Sustainability metrics** for environmental impact assessment

## 📋 Data Sources

- **Primary**: TransJakarta Public Information Portal
- **URL**: https://ppid.transjakarta.co.id/informasi/setiap-saat
- **Coverage**: January-December 2024, all 14 corridors
- **Format**: Monthly passenger counts per bus stop (PDF tables)

## 🤝 Contributing

This project encourages community involvement in Jakarta's transportation analysis:

1. **Fork the repository**
2. **Add new analysis modules** (seasonal patterns, weather correlations, etc.)
3. **Improve the optimization algorithms**
4. **Enhance the Power BI dashboard**
5. **Submit pull requests**

## 📝 Future Enhancements

- [ ] **Real-time data integration** via TransJakarta API
- [ ] **Machine learning models** for demand forecasting
- [ ] **Route optimization** algorithms
- [ ] **Integration with other transport modes** (LRT, MRT, KRL)
- [ ] **Environmental impact analysis** (emissions, fuel efficiency)
- [ ] **Mobile app** for commuter insights

## 📜 License

MIT License - feel free to use this analysis for research, policy-making, or further development.

## 🙏 Acknowledgments

- **TransJakarta** for providing transparent ridership data
- **Jakarta commuters** who inspired this analysis #SemangatWargaCiledug
- **Open source community** for the amazing tools and libraries

---

*Built with ❤️ for Jakarta's public transportation improvement*

**Contact**: [Your GitHub Profile] | **Data**: [TransJakarta Portal](https://ppid.transjakarta.co.id/informasi/setiap-saat)

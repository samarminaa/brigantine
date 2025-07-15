### 🌊 **Project Title**: *"Brigantine by the Block: Real Estate Trends & Public Investment in a Coastal Town"*

---

### 🔍 **Project Goal**:

Build a dbt-powered data model and Looker dashboard that explores **real estate trends**, **demographics**, and **local government investment** in Brigantine, NJ over time — useful for residents, planners, and civic advocates.

---

### 📦 **Data Sources Specific to Brigantine, NJ**:

| Data Type | Source | Notes |
| --- | --- | --- |
| **Home prices** | Zillow Research → Zillow Home Value Index (ZHVI) | Search by zip code `08203` |
| **Property assessment and tax records** | Atlantic County Open Data or NJ PARCEL | Parcel-level data includes assessed value, property use, etc. |
| **Demographics** | U.S. Census ACS 5-Year Estimates | Download block-group or tract-level data for Brigantine |
| **Public infrastructure & services** | NJDEP Open Data, Brigantine city budget or city council meeting minutes | Try to find data on flood control, parks, road maintenance, etc. |
| **FEMA Flood Zones** | FEMA Flood Map Service Center | Use to see if flood risk correlates with housing price stagnation or growth |

---

### 🛠️ **dbt Modeling Structure**

**Raw Data (`raw_*`)**

- `raw_home_prices` (from Zillow)
- `raw_property_tax` (from Atlantic County)
- `raw_census` (from ACS)
- `raw_city_budget` (manually input CSV if needed)

**Staging Models (`stg_*`)**

- Standardize zip/tract identifiers, property types, dates, etc.

**Core Models**

- `dim_blockgroup`: Geo + population + income
- `fct_home_prices`: Prices by zip/tract/year
- `fct_tax_assessments`: Taxable property values over time
- `fct_public_spending`: Park, stormwater, road spending per year
- `fct_flood_risk`: Overlay FEMA flood zones with parcels

**Optional Analytics Models**

- `agg_growth_vs_investment`: Public $ vs. price growth
- `agg_risk_adjusted_value`: Home values relative to flood risk or storm infrastructure investment

---

### 📊 **Looker Dashboard Modules**

1. **Real Estate Overview**
    - Median home value trend (line chart)
    - Avg tax assessment by year
    - Map of properties by assessed value
2. **Infrastructure + Risk**
    - Spending per resident on roads/parks
    - Map: flood zones vs. property value change
    - Investment vs. home value growth by neighborhood
3. **Equity + Demographics**
    - Income vs. property taxes
    - Race & age distributions across tracts
    - Public investment per capita by block group

---

### 💡 Beginner Tips:

- Start with **Zillow + ACS data**, build 2–3 models, and create a simple “Neighborhood Profile” dashboard.
- Add more layers like **property tax or flood data** later as you practice joins and spatial mapping.
- If you can’t find a data portal for Brigantine itself, Atlantic County and NJ state datasets usually include it.

---

# Housing Data Central

## Overview
A housing market dashboard that displays various economic indicators from FRED (Federal Reserve Economic Data) via a Cloudflare proxy. The dashboard shows charts for mortgage rates, home sales, inventory, construction data, and other economic metrics.

## Project Structure
- `index.html` - Main dashboard with KPI tiles and economic charts
- `new-homes.html` - New Homes Pipeline Dashboard showing permits → starts → sales flow with indexed charts
- `raw-data.html` - Raw Data Explorer for viewing individual FRED series with Y/Y and Q/Q changes
- `server.js` - Simple Node.js static file server for development

## Technology Stack
- **Frontend**: Vanilla HTML/CSS/JavaScript
- **Charting**: Chart.js (loaded via CDN)
- **Data Source**: FRED API via Cloudflare proxy at `https://fred-proxy.patrick-grow.workers.dev`
- **Server**: Node.js HTTP server for static file serving

## Running the Project
The project runs on port 5000 using the Node.js server:
```
node server.js
```

## Pages

### Main Dashboard (index.html)
- KPI tiles for key housing metrics
- Interactive charts with recession shading
- Global controls for date range

### New Homes Pipeline (new-homes.html)
- **Flow Chart**: Permits, Starts, Sales indexed to a selectable base year (2000-2024)
- **Stock Chart**: Under Construction and Inventory levels with dual Y-axes
- **KPI Cards**: Latest values with YoY changes and Backlog Ratio (months of pipeline)
- Time range selector (5-20 years)

### Raw Data Explorer (raw-data.html)
- Browse individual FRED series organized by category
- Time range filtering (2-20 years)
- Bar chart with Y/Y change line overlay
- Data table with Y/Y and Q/Q change columns

## Data Sources
All data is fetched from FRED series via the Cloudflare proxy:

### Main Dashboard
- USAUCSFRCONDOSMSAMID - Zillow ZHVI (home values)
- MORTGAGE30US - 30-year mortgage rate
- EXHOSLUSM495S - Existing home sales
- HOSSUPUSM673N - Existing home months supply
- HNFSEPUSSA - New homes for sale
- MSACSR - New homes months supply
- HOUST1F - Single-family starts
- CES2023610001 - Residential construction employees
- UMCSENT - Consumer sentiment
- UNRATE - Unemployment rate
- USREC - Recession indicator (for chart shading)

### New Homes Pipeline
- PERMIT1 - Single-family building permits
- HOUST1F - Single-family housing starts
- HSN1F - New single-family home sales
- UNDCON1USA - Single-family homes under construction
- HNFSEPUSSA - New homes for sale (inventory)

# Housing Data Central

## Overview
A housing market dashboard that displays various economic indicators from FRED (Federal Reserve Economic Data) via a Cloudflare proxy. The dashboard shows charts for mortgage rates, home sales, inventory, construction data, and other economic metrics.

## Project Structure
- `index.html` - Main single-page application with all HTML, CSS, and JavaScript
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

## Features
1. **Median Monthly Payment & Mortgage Rate** - Calculates estimated P&I payment based on home prices and 30-year mortgage rates with adjustable down payment
2. **Existing Home Sales** - Shows SAAR and months supply
3. **New Home Inventory** - New homes for sale and months supply
4. **Single-Family Starts** - Housing starts with YoY percentage change
5. **Residential Construction Workers** - Employment data with YoY change
6. **Consumer Sentiment & Unemployment** - Economic indicators
7. **AI Commentary** - Automated insights from the proxy service

## Data Sources
All data is fetched from FRED series via the Cloudflare proxy:
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

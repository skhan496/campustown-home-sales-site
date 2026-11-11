# Home prices in college towns

This static site compares median home sale prices across 18 college towns using the College-town home sales dataset. A bar chart and table show each city's median and the number of eligible sales behind it.

## View the site

GitHub Pages publishes the repository root directly through `.github/workflows/pages.yml`. Enable Pages with **GitHub Actions** as the source in repository settings. Once published, the site reads `data/college_town_home_sales.csv` using a relative path.

## How to read the figures

The site includes completed sales with `sale_price` of at least $1,000, as required by the dataset documentation. It groups by the recorded city and state, calculates the median sale price for each group, and rounds displayed dollar amounts to whole dollars. The table also reports eligible sale counts. Cities are sorted by median price, highest first.

The median is the center value after sorting prices (the mean of the two center values when a group has an even number of sales). The source notes that prices are reported by the collection source and are not independently verified against county records. Values above the $1,000 minimum may still be implausible. See `docs/data_description_sheet.md` for dataset details and caveats.

## Data and tools

The source CSV contains 35,442 sales and 34 fields. The site uses only city, state, and sale price. It is built with plain HTML, CSS, and JavaScript; there are no package dependencies or build step. The page reads the CSV in the browser, so the published root must include the `data/` directory.

The dataset is also provided as Excel, SQLite, DuckDB, and Parquet files for independent review. In SQLite and DuckDB, the table is named `home_sales`. Do not edit any of the five source dataset files. Read `docs/data_description_sheet.md` before extending the analysis; keep ZIP codes, county FIPS codes, and parcel numbers as text.

## Citation

College-town home sales dataset, version 1.0 (2026). University of Illinois-Deloitte Foundation Center for Business Emerging Technologies. Data collected March 2026.

## Home size and sale price

The scatter plot titled “Do bigger homes sell for more?” uses `living_area_sqft` on the horizontal axis and `sale_price` on the vertical axis, with one dot per included sale. It excludes missing or nonpositive living area, prices below $1,000, and prices above $5,000,000. The data description identifies zero square-foot living areas as invalid, prices below $1,000 as implausible, and sales above $5 million as extreme. The upper limit keeps these documented extremes from compressing the rest of the chart. The plotted sale count is shown with the chart.
## Visualization Choices

I chose to explore two questions using the college-town home sales dataset:

1. **How do median home sale prices compare across college towns?** I used a bar chart to compare typical sale prices across the 18 cities and towns.

2. **Do bigger homes sell for more?** I used a scatter plot to explore the relationship between living area (square feet) and sale price.

I selected these visualizations because I wanted to compare housing affordability across college towns and explore how property size relates to sale price.

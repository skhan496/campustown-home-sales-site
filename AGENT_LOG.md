# Agent log

## 2026-11-11: Build city median-price homepage

- **Asked:** "I approve your proposed plan to build the homepage, bar chart, and table showing median home sale prices by city, excluding sales below $1,000. Please pull the latest main branch first, then proceed with the changes. Update the README and AGENT_LOG.md as required by AGENTS.md."
- **Agent produced:** Replaced the placeholder with a responsive static page that reads the CSV, groups eligible sales by city and state, and displays median prices in a ranked bar chart and table with eligible sale counts. Updated the README with the metric definition, dataset caveats, and publication workflow.
- **Checked or changed:** Read `AGENTS.md` and `docs/data_description_sheet.md` before analysis. Fetched `origin/main` (available revision `183aa26`). Independently calculated group sizes and medians from the CSV in Python to confirm the expected 18 city groups and 35,438 eligible sales; for an even-sized group, the median can include 50 cents, and the site rounds displayed prices to whole dollars.

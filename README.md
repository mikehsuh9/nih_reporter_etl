# National Institutes of Health (NIH) Tobacco, Nicotine & Electronic Nicotine Delivery Systems (ENDS) Research Funding Explorer

Explores how NIH funds tobacco, nicotine, and END research. It is built for public health communications strategists who need a clear view of where dollars go.

## Data source

NIH [RePORTER Project API v2](https://api.reporter.nih.gov/) :

- The Research, Condition, and Disease Categorization (RCDC) spending categories **852** (Tobacco), **791** (Smoking and Health), **4721** (Electronic Nicotine Delivery Systems)
- Fiscal years **2020–2024**
- US organizations only; subprojects excluded

## Run the ETL

```bash
pip install -r requirements.txt
jupyter notebook nih_reporter_etl.ipynb
```

Run all cells. Output: `data/tobacco_nih_awards.csv`

## Output

`data/tobacco_nih_awards.csv` — one row per award-year record (3,018 rows), with project details, award amount, organization geography, administering institute, and RCDC spending categories.

## Visualization

Interactive dashboard on Tableau Public: https://public.tableau.com/shared/5NPDCC64R?:display_count=n&:origin=viz_share_link

## Notes

- ~10% of award dollars lack `org_state` in the source data (shown as unassigned geography in the viz).
- RCDC categories overlap; a single award can match multiple tobacco-related categories.
- 3,018 records after deduplication on `appl_id` + `fiscal_year`.

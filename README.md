# hmrl-gtfs

GTFS (General Transit Feed Specification) dataset for Hyderabad Metro Rail Ltd (HMRL).

## Source & download

- Official HMRL Open Data page: <https://hmrl.co.in/open-data/>
- Original GTFS download (public link referenced by HMRL): <https://hmrl.co.in/open-data/> (follow the "Open Data" instructions and download link provided by HMRL)

This repository contains the standard GTFS text files describing transit schedules, routes, stops, shapes, fares, and calendar data.

## Contents

The repository includes the following GTFS files:

- `agency.txt`
- `stops.txt`
- `routes.txt`
- `trips.txt`
- `stop_times.txt`
- `calendar.txt`
- `shapes.txt`
- `feed_info.txt`
- `fare_attributes.txt`
- `fare_rules.txt`

Each file follows the GTFS format (comma-separated values with required and optional columns). These files are stored as plain `.txt` CSV files in the repository root.

## Terms of use / attribution

This dataset is published by Hyderabad Metro Rail Ltd. By using the data you agree to HMRL's terms of use available on their Open Data page. Key points (summary):

- Access to this data is free and may be used for commercial and non-commercial applications.
- HMRL retains all rights and requires attribution. Use the following attribution statement when using or redistributing this data:

"Contains data provided by Hyderabad Metro Rail Ltd."

- The data is provided "AS IS" without warranty; HMRL is not liable for errors, omissions, or any losses resulting from its use.
- You must not imply endorsement by HMRL and must comply with applicable laws. See the full terms at <https://hmrl.co.in/open-data/>.

## Quick usage

Preview or inspect files using common CLI tools:

```bash
# list files
ls -1

# view first lines of a file
head -n 10 stops.txt

# pretty-print CSV (install csvkit: pip install csvkit)
csvlook stops.txt | less -S

# quick statistics (csvkit)
csvstat --count stops.txt
```

Use Python/pandas for quick exploration:

```bash
python - <<'PY'
import pandas as pd
print(pd.read_csv('stops.txt').head())
PY
```

If you need to validate the feed with tools that expect a zipped GTFS feed, create a zip first:

```bash
zip -r hmrl-gtfs.zip *.txt
```

Then run a GTFS validator (example, Google GTFS Validator - Java-based):

```bash
java -jar gtfs-validator.jar hmrl-gtfs.zip
```

## Contributing

- Open issues to report problems or suggest improvements.
- Send pull requests with clear change descriptions and the source/origin of updated data.

See also

- HMRL Open Data: <https://hmrl.co.in/open-data/>
- If you redistribute copies of this dataset, please include the attribution statement above.

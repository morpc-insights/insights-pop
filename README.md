# Data Kit - Total population by year

## Version

Current version: 2024-11-14

## Provider

  - Organization: [Mid-Ohio Regional Planning Commission](https://morpc.org)
  - Contact: 
    - Name: Adam Porr
	- E-mail: aporr@morpc.org
	- Phone: 614-233-4216

## Introduction

This data kit consists of the best available set of population facts for the Central Ohio region and its constituent counties and communities. Historic data includes decennial census counts from 1980 to 2020 (reference date April 1), annual intercensal estimates from 2000 to 2020 (reference date July 1), and MORPC annual estimates from 2020 to 2024 (reference date January 1). Historic data comes from the Census Population Estimates Program, including intercensal estimates where available and the latest vintage post-censal estimates otherwise.  Forecasted data is available for five-year intervals between 2025 and 2050.  Forecasted values come from county-level and summarized GridMAZ-level forecasts produced for the 2024 MTP.  The 80% confidence limits are provided for the region-level and county-level forecasts.  Users are advised that the MORPC annual estimates are not intended for use as a time series and generally should not be compared year-over-year.


## Outputs

This data kit includes one output which consists of a long-form table that includes the combined population facts in a common schema. Each record represents a population fact of a single type (count, estimate, or forecast) for one geography in one year. The data is provided in `./output_data/morpc-insights-pop-temporal.csv`.  The output is accompanied by a [Frictionless Resource file](https://specs.frictionlessdata.io/data-resource/), which provides a high-level description of the data and a link to the associated table schema.  The Resource file also provides the [MD5 checksum](https://en.wikipedia.org/wiki/Md5sum) ("hash") and the file size ("bytes") of the data file to allow for integrity checking.

The table schema is described by a [Frictionless Schema file](https://specs.frictionlessdata.io/table-schema/), which describes each of the fields contained in the table, including its name and type, and provides additional metadata about the table.

## Processes

The outputs are produced by a fully-automated process implemented as a Jupyter notebook (`./morpc-insights-pop-temporal.ipynb`). The script retrieves the population facts from the outputs of upstream workflows and assembles them into a single table.  The only transformations applied to the data are those necessary to standardize their schemas, which may include adding or removing fields, renaming fields, changing field order, and sometimes changing data types.

## Inputs

The process requires one input, specifically the combined table of population facts produced by the morpc-pop-collect workflow. This table includes population counts, estimates, and forecasts from a variety of sources.  See (`./input_data/morpc-pop-collect.csv`)

## Revision history

Revisions are listed in reverse chronological order.

### 2024-11-14 Adam Porr <aporr@morpc.org>

Initial release for use in Insights platform prototype.

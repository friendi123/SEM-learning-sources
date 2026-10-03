# SEM learning sources

Practice data for path analysis and structural equation modeling (SEM).

## `path.dat`

Test scores for 200 high-school students: 200 rows, 4 columns, comma-separated, **no header row**.

| Column | Variable | Description | Mean | SD | Range |
|---|---|---|---|---|---|
| 1 | `read` | Reading score | 52.23 | 10.25 | 28-76 |
| 2 | `write` | Writing score | 52.78 | 9.48 | 31-67 |
| 3 | `math` | Math score | 52.64 | 9.37 | 33-75 |
| 4 | `socst` | Social studies score | 52.40 | 10.74 | 26-71 |

No missing values. Pairwise correlations range from 0.54 to 0.66.

## Source

The rows match, in the same order, the `read`, `write`, `math`, and `socst` columns of `hsb2`,
a 200-student sample from the *High School and Beyond* survey distributed by the UCLA
Statistical Methods and Data Analytics group (OARC):
<https://stats.oarc.ucla.edu/stat/data/hsb2.csv>.
The other `hsb2` columns (id, gender, race, socioeconomic status, school type, program, science score) are not included.

## Loading the data

R:

```r
library(data.table)
path_data <- fread("path.dat", header = FALSE,
                   col.names = c("read", "write", "math", "socst"))
```

Python:

```python
from pathlib import Path
import pandas as pd

path_data = pd.read_csv(Path("path.dat"), header=None,
                        names=["read", "write", "math", "socst"])
```

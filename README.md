# Library Defaulters Data Challenge

This repository contains code for analysis and prediction of default (not returning borrowed books) rates for library data. 

## File Organization

```
.
├── README.md
├── description.md
├── eda
│   ├── 0_eda_libraries.ipynb
│   └── 1_eda_checkouts.ipynb
├── figures
│   └── library_map.html
└── models

```


## Overview of Files

| File                     | Directory                     | Description                                                  | Dependencies                                                    |
| :---------------------------- | :-------------------- | :----------------------------------------------------------- | :---------------------------- |
0_eda_libraries.ipynb | ./eda | Cleaning and exploratory analysis of the libraries dataset | None |
1_eda_checkouts.ipynb | ./eda | Cleaning and exploratory analysis of the checkouts dataset | None | 
library_map.html | ./figures | Figure showing location of the 18 libraries on the map of Portland OR | ./eda/0_eda_libraries.ipynb |
# Library Defaulters Data Challenge

This repository contains code for analysis and prediction of default (not returning borrowed books) rates for library data. 

## File Organization

**Repository**

```
.
├── README.md
├── figures
│   └── library_map.html
├── prediction_models.ipynb
└── preprocessing_eda
    ├── books.ipynb
    ├── checkouts.ipynb
    ├── customers.ipynb
    └── libraries.ipynb
```

**Data Directory (not included)**

```
.
├── Data\ Challenge
│   ├── books.csv
│   ├── checkouts.csv
│   ├── customers.csv
│   └── libraries.csv
├── cleaned_data
│   ├── books_checkouts_merged.csv
│   ├── books_cleaned.csv
│   ├── checkouts_cleaned.csv
│   ├── customers_cleaned_geocoded.csv
│   ├── libraries_cleaned_geocoded.csv
│   └── merged.csv
└── library_defaulters
```

## Business Questions

**Are there any factors you can find that are connected with late returns?**
I was able to find several factors related to late returns, the most prominent amongst these were: 
- distance between the patron home address and the library address. Patrons returning books late on average lived 3 kilometers further away than those returning books on time
- proximity of due date to a holiday. I checked both if the due date for a return was a holiday, and the distance between the due date and the closest holiday (in days). Checkouts associated with late returns were on average closer to holidays (when excluding checkouts in the 19th century). 
- the day of the week that the due date is. Late returns were more common on Tuesdays, than other days of the week. 
- number of pages in the book. Longer books were returned late more often. 

---

**What would you recommend the library do to mitigate the risks you find?**
I would make two primary recommendations: 

- to install drop-boxes, especially further away from the library, that patrons can drop the books they're returning to. This would reduce the distance between patron address and "return point" 
- to allow for extended return-windows around holidays. Since holidays appear to be an important feature in the data, my ananlysis is that peple are preoccupied (traveling, hosting family etc) during holidays leading to missing the due dates. Once the due dates are missed, they might slip into the "it's late anyway" thought process, causing further delays-- this is something I'd like to test since we have data on duration borrowed and actual return dates.
---

**What other stories can you tell with this data?**
I think a lot of the patterns of when people return books once they've already missed the due date can be interesting to tease out, as well as informative about what are optimal conditions for returning books. For example: 
- how long do patrons keep a book for after they've missed the due date? 
- what days of the week are "past due date" books often returned? 
- what is the relationship with number of pages and days a book is borrowed for? Is there a threshold level such that books shorter than that are always returned on time? 


## Additional Exercises
These are the exercises I would have undertaken if I had more time: 
- the data suffers from class imbalance, so undertake techniques to account for that such as minority-class oversampling or majority class undersampling
- recursive feature eliminatior for an improved feature selection
- a simple neural network (with softmax layer) to get the probabilities of late and timely return 
- set-up pipelines and create classes to avoid repitition when reusing code for different models 
- use google's Place API to see if the library is close to a grocery store, or downtown, or any other area that might be visited frequently


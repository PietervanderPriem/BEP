## Project Proposal

### Introduction

This project is focused on the Python code infrastructure and implementation to enable programmatically scanning through datasets and programming assignments. The final deliverable is a CLI (Command Line Interface) tool which will allow the end-user to achieve two things:
- find programming assignments based on datasets
- find datasets based on programming assignments

Proposed research questions:
- Is it possible to automatically process unseen datasets to be used for programming assignments?
- Can solutions to programming assignments be generated from a template for unseen datasets?

Currently, finding datasets and programming assignments takes up a lot of manual labour, which is time not spend teaching students. Therefore, it would be very beneficial if this process could be (partially) automated. This would free up time for teachers, which will improve the quality of education. In addition to this students will have the ability to practice a lot more with novel assignments.

### Methodology

To deal with these problems, a CLI tool will be developed to automate part of this process. This tool has to deal with the following challenges:
 - Crawl sites which aggregate datasets -> Beautifulsoup?
 - Ingesting datasets -> check for header, separator, extension etc.
 - Feature generation, what metris are informative for tasks and datasets -> nr. of observations, types of features, min max, common feature names etc.
 - Classification
   - Tasks
   - Datasets
 - Mapping tasks to datasets
 - Mapping datasets to tasks

### Planning

V1 - DL 01-04-2023 23:59

Automatically process predefined datasets. Enable basic functionality for fetching predefined programming tasks based on predefined datasets and vice versa.

V2 - DL 15-05-2023 23:59

Expand functionality to unseen datasets. Add functionality to get from url and classify accordingly.

V3 - DL 01-06-2023 23:59

Enable crawling on predefined public dataset aggregators, i.e. AWS public datasets.

Optional V4 - DL 15-06-2023 23:59

Generate solutions to progamming assignments automatically based on a solution template and specified dataset.


Code structure: 

```
.
├── src/
│   ├── cli (Pieter)/
│   │   ├── main.py (V1)
│   │   ├── command_1.py (V1)
│   │   ├── command_2.py (V1)
│   │   ├── command_3.py (V2)
│   │   └── etc.
│   └── client/
│       ├── task (Vera)/
│       │   ├── task_model.py (V1)
│       │   ├── create.py (V2)
│       │   ├── read.py (V1)
│       │   ├── update.py (V2)
│       │   └── delete.py (V2)
│       ├── dataset (Vera)/
│       │   ├── dataset_model.py (V1)
│       │   ├── create.py (V2)
│       │   ├── read.py (V1)
│       │   ├── update.py (V2)
│       │   └── delete.py (V2)
│       ├── data (Pieter)/
│       │   └── loader/
│       │       ├── main.py (V1)
│       │       ├── from_processed.py (V1)
│       │       ├── from_raw.py (V2)
│       │       ├── classify.py (V2)
│       │       ├── write_to_storage.py (V2)
│       │       └── crawl_aggregator.py (V3)
│       └── classify (Vera - V1)/
│           ├── get_tasks (Emma)
│           └── get_datasets (Imme)
└── temp/
    └── datasets (Pieter - V1)/
        ├── example_dataset_1.csv
        └── example_dataset_2.csv
```


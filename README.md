# aimms-santa-2023

A simple AIMMS project designed for the Kaggle Santa 2023 Challenge.

[Link to Kaggle Challenge](https://www.kaggle.com/competitions/santa-2023/)

## Quick Start

To run the project, utilize the `MainExecution` procedure.

## Additional Information

### Overview

This project provides essential data structures and procedures to address the Kaggle Santa Challenge of 2023. In its initial version, it focuses on generating the sample submission file without further optimization.

### Data Handling

Parquet files containing all necessary data for individual IDs are included in the `parquet` folder. You can either regenerate them or read directly, improving the model's performance compared to processing raw data.

### Key Procedures and Structures

- **pr_importAllFiles**: Reads files (puzzle_info.csv, puzzles.csv, sample_submission.csv) in the Download folder, populating data structures in the Import section.

- **pr_exportSubmissionFile**: Exports resulting moves stored in the `sp_moves(i_id)` identifier within the export section.

- **pr_transformImportToDataModel**: Transforms data from the Import section to the Data model based on a selected ID in the `ep_runID` element parameter. Resulting data is available in the Data Model Section.

- **pr_transformAllowedMovesData**: Transforms data from Import section to Data model specifically on the possible moves based on the puzzle type of the selected ID in the `ep_runID` element parameter. Resulting data is available in the Data Model Section.

- **pr_generateOppositeMoves**: Generates opposite moves to currently included moves (e.g., if there are moves f0, f1, d0, and d1, it will generate -f0, -f1, -d0, and -d1).

- **pr_generateNoneMove**: Generates a movement called 'none' that does not change any position.

- **pr_processingAndParquetGeneration**: Imports all data from files, processes each one individually, and stores the resulting data in individual parquet files in the "parquet" folder.

### TODO

- Implement a simple solution generator.
- Develop a user interface (UI).
- Incorporate direct calls to Kaggle site for downloading and uploading.

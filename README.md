# UK Food Hygiene Ratings Analysis

## Overview

The UK Food Standards Agency evaluates various establishments across the United Kingdom and assigns them food hygiene ratings. In this challenge, we will evaluate some of the ratings data to help the editors of Eat Safe, Love magazine decide where to focus future articles. This challenge is divided into three parts: database setup, database update, and exploratory analysis.

## Challenge Structure

### 1. Database and Jupyter Notebook Setup

**File**: `NoSQL_setup_starter.ipynb`

1. **Import Data**:
   - Import data from `establishments.json` into a MongoDB database named `uk_food` and a collection named `establishments`.
   - Copy the import command used in the terminal to a markdown cell in the notebook.

2. **Library Imports**:
   - Import the necessary libraries: PyMongo and Pretty Print (`pprint`).

3. **Create MongoDB Client**:
   - Create an instance of the MongoDB client.

4. **Confirm Database and Data**:
   - List databases to confirm `uk_food` is listed.
   - List collections to ensure `establishments` is present.
   - Display one document from the `establishments` collection using `find_one` and `pprint`.
   - Assign the `establishments` collection to a variable for further use.

### 2. Update the Database

**File**: `NoSQL_setup_starter.ipynb`

1. **Add New Restaurant**:
   - Add a new halal restaurant in Greenwich to the database with the following information:
    ```json
    {
        "BusinessName": "Penang Flavours",
        "BusinessType": "Restaurant/Cafe/Canteen",
        "BusinessTypeID": "",
        "AddressLine1": "Penang Flavours",
        "AddressLine2": "146A Plumstead Rd",
        "AddressLine3": "London",
        "AddressLine4": "",
        "PostCode": "SE18 7DY",
        "Phone": "",
        "LocalAuthorityCode": "511",
        "LocalAuthorityName": "Greenwich",
        "LocalAuthorityWebSite": "http://www.royalgreenwich.gov.uk",
        "LocalAuthorityEmailAddress": "health@royalgreenwich.gov.uk",
        "scores": {
            "Hygiene": "",
            "Structural": "",
            "ConfidenceInManagement": ""
        },
        "SchemeType": "FHRS",
        "geocode": {
            "longitude": "0.08384000",
            "latitude": "51.49014200"
        },
        "RightToReply": "",
        "Distance": 4623.9723280747176,
        "NewRatingPending": True
    }
    ```

2. **Update Restaurant Information**:
   - Find the `BusinessTypeID` for "Restaurant/Cafe/Canteen".
   - Update the new restaurant with the found `BusinessTypeID`.

3. **Remove Dover Establishments**:
   - Check the number of documents with the Dover Local Authority.
   - Remove establishments within the Dover Local Authority.
   - Confirm the removal.

4. **Convert Data Types**:
   - Convert latitude and longitude to decimal numbers using `update_many`.
   - Convert `RatingValue` to integer numbers using `update_many`.

### 3. Exploratory Analysis

**File**: `NoSQL_analysis_starter.ipynb`

Use the following questions to explore the database:

1. **Hygiene Score of 20**:
   - Find establishments with a hygiene score equal to 20.

2. **RatingValue >= 4 in London**:
   - Find establishments in London with a `RatingValue` greater than or equal to 4.

3. **Top 5 Establishments near Penang Flavours**:
   - Find the top 5 establishments with a `RatingValue` of 5, sorted by lowest hygiene score, nearest to "Penang Flavours".

4. **Hygiene Score of 0 by Local Authority**:
   - Find the number of establishments in each Local Authority area with a hygiene score of 0. Sort the results from highest to lowest and display the top ten.


---

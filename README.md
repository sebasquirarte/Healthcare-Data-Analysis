![healthcare_cover](https://github.com/sebasquirarte/Healthcare-Data-Analysis/assets/39809366/9ef27888-a2e8-44ff-9ba1-641d96a87a41)
Sebastian Quirarte | sebastianquirajus@gmail.<nolink>com | in/sebastianquirarte | Last Updated: Dic 10 2023

# Objective

The aim of this project was to use PosgreSQL to create tables, load healthcare data, filter and tranform it using basic SQL queries, as well as creating a dashboard in Tableau to visualize it. 

# Skills Practiced
- PostgreSQL
- Tableau
- SQL queries
- Data manipulation
- Data analysis
- Data visualization

# Data

Healthcare data was originally created with [Synthea™](https://synthetichealth.github.io/synthea/), an open-source, synthetic patient generator that models realistic medical history of synthetic patients. This projet is based on the YouTube video: ["SQL Basics with Healthcare Data"](https://www.youtube.com/watch?v=ef4CAu-OwvM) by [Data Wizardry](https://www.youtube.com/@DataWizardry) and the text files used to load the data were downloaded from their [website](https://datawizardry.academy/sql-basics-healthcare/).

The tables that were created from the text files using SQL are as follows:

### Conditions
_Medical diagnosis of patients registered at hospital, includes code and description, among others. **156,945 rows**._

### Encounters
_Medical encounter of patients, includes class, code, description, cost, and coverage, among others.  **455,935 rows**._

### Immunizations
_Applied immunizations, includes code and description, among others. **165,493 rows**._

### Patients
_Patient data such as birthdate, ssn, name, race, gender, address, among others. **11,363 rows**._

# Overview

The SQL queries used implement the [SQL Style Guide by Simon Holywell](https://www.sqlstyle.guide/).

### **Creating tables and loading data**

To start off, we create our four tables using the following SQL query in PostgreSQL's *Query Tool*.

~~~~sql
-- Creates 'conditions' table --      
       CREATE TABLE conditions (
              start DATE,
               stop DATE,
            patient VARCHAR(1000),
          encounter VARCHAR(1000),
               code VARCHAR(1000),
        description VARCHAR(200));

-- Creates 'encounters' table --
             CREATE TABLE encounters (
                 id VARCHAR(100),
              start TIMESTAMP,
               stop TIMESTAMP,
            patient VARCHAR(100),
       organization VARCHAR(100),
           provider VARCHAR(100),
              payer VARCHAR(100),
    encounter_class VARCHAR(100),
               code VARCHAR(100),
        description VARCHAR(100),
base_encounter_cost FLOAT,
   total_claim_cost FLOAT,
     payer_coverage FLOAT,
        reason_code VARCHAR(100));

-- Creates 'immunizations' table --
       CREATE TABLE immunizations (
               date TIMESTAMP,
            patient VARCHAR(100),
          encounter VARCHAR(100),
               code INT,
        description VARCHAR(500));

-- Creates 'patients' table --
       CREATE TABLE patients (
                 id VARCHAR(100),
          birthdate DATE,
          deathdate DATE,
                snn VARCHAR(100),
            drivers VARCHAR(100),
           passport VARCHAR(100),
             prefix VARCHAR(100),
              first VARCHAR(100),
               last VARCHAR(100),
             suffix VARCHAR(100),
             maiden VARCHAR(100),
            marital VARCHAR(100),
               race VARCHAR(100),
          ethnicity VARCHAR(100),
             gender VARCHAR(100),
         birthplace VARCHAR(100),
            address VARCHAR(100),
               city VARCHAR(100),
              state VARCHAR(100),
             county VARCHAR(100),
               fips INT,
                zip INT,
                lat FLOAT,
                lon FLOAT,
healthcare_expenses FLOAT,
healthcare_coverage FLOAT,
             income INT,
                mrn INT);
~~~~

Next, we load our data by importing the corresponding text files (making sure to import as .txt and not .csv) into their respecitve tables direclty in PostgreSQL.

![healthcare_1](https://github.com/sebasquirarte/Healthcare-Data-Analysis/assets/39809366/b6a91249-54e9-4bca-8354-6787b8715481)

# Results


### Tableau Dashboard [LINK]


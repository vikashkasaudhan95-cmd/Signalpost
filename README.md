# 🌍 CompanyInfoAgent — Signalpost Project

## 🏁 Introduction

Welcome to **CompanyInfoAgent**, a data‑driven project built for the **Signalpost/Builderr Project**.  
This project showcases how automation, clean data engineering, and intuitive UI design can come together to create a **Norwegian Company Research Agent**
— capable of validating and displaying company information sourced from **the Brønnøysund Register Centre**.


The goal:  

> To build a reliable, verifiable, and visually engaging dataset of **1000 Norwegian company/entity records**,
>  integrated into a responsive web interface for instant lookup and validation.
--------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🧠 Project Highlights

- 🔹 **Dataset Automation:** Scripts automatically fetch and merge company data from the Brønnøysund API.  
- 🔹 **Data Validation:** Ensures every record has unique organization numbers, normalized fields, and ISO timestamps.  
- 🔹 **Frontend Integration:** A clean, modern UI built with HTML, CSS, and JavaScript for company dataset search and lookup.
- 🔹 **Hackathon‑Ready Submission:** Fully documented, verified, and visually demonstrated with dataset statistics.


## 📂 Project Structure

CompanyInfoAgent
│
├── index.html
│   └── Main web application
│
├── style.css
│   └── Application styling
│
├── script.js
│   └── Search and frontend logic
│
├── companies.json
│   └── Final validated company dataset
│
├── normalize_merge.js
│   └── Dataset merge and normalization
│
├── validate_and_finalize.js
│   └── Dataset validation and finalization
│
└── README.md
    └── Project documentation

Technology Stack

Frontend
- HTML5
- CSS3
- JavaScript
Data
- JSON
- Brønnøysund Register Centre public registry data
UI
- CSS Grid
- Flexbox
- Responsive design
- Browser-based company lookup

-------------------------------------------------------------------------

## 🗃 Dataset Overview

**File:** `companies.json`  
**Records:**  1,000 unique company/entity records 
**Source:** [Brønnøysund Register Centre API](https://data.brreg.no/enhetsregisteret/api/enheter/)  


### 🧩 Data Fields

| Field | Description |
|-------|--------------|
| `name` | Company name |
| `orgNumber` | Unique organization number |
| `founded` | ISO date (`YYYY-MM-DD`) when available |
| `address` | Address information stored as an array or string depending on the record |
| `updated` | ISO‑8601 UTC timestamp |
| `source` | API link for verification |

### 🧹 Normalization Rules
- Missing optional fields are preserved when unavailable.
- Deduplicated by `orgNumber`  
- Address stored in a structured format, with array or string representation depending on the record.
- Timestamps standardized to ISO‑8601 UTC  
- Dataset size: **1,000 records**

Dataset Snapshot

╔══════════════════════════════════════╗
║          CompanyInfoAgent    
║
╠══════════════════════════════════════╣
║
  Company Profiles              1,000
║
║
  Unique Org Numbers            1,000
║
║  
  Duplicate Org Numbers             0
║
║ 
  Source URLs                   1,000
║
║ 
  Founded Dates                   806
║
║ 
  Address Fields                1,000
║
║ 
  Array Addresses                 960 
║
║ 
  String Addresses                 40 
║
╚══════════════════════════════════════╝
  

## ⚙️ Validation Workflow
1. **Merge fragments** → `normalize_merge.js`  
2. **Normalize fields** → founded, address, updated, source  
3. **Deduplicate** → by `orgNumber`  
4. **Validate** → run `validate_and_finalize.js`  
5. **Output** → `companies.json` (final dataset)

### ✅ Example Record
```json
{
  "name": "- P A L M E R A -",
  "orgNumber": "916627939",
  "founded": "2015-11-01",
  "address": ["Strandgaten 208"],
  "updated": "2026-10-02T11:35:29.164Z",
  "source": "https://data.brreg.no/enhetsregisteret/api/enheter/916627939"
}
----------------------------------------------------------------------------

## How It Works

                  USER
                   │
                   ▼
        Enter Organization Number
                   │
                   ▼
          CompanyInfoAgent
                   │
                   ▼
          Search Company Data
                   │
                   ▼
             companies.json
                   │
                   ▼
        Matching Company Record
              ┌────┴────┐
              │         │
              ▼         ▼
        Company Facts  Source URL
              │         │
              └────┬────┘
                   ▼
              Verification
                   │
                   ▼
               User Result
-------------------------------------------------------------

Data Preparation Workflow

        Public Registry Data
                 │
                 ▼
          Collect Records
                 │
                 ▼
       Merge Data Fragments
                 │
                 ▼
        Normalize Fields
                 │
                 ▼
        Remove Duplicates
                 │
                 ▼
        Validate Dataset
                 │
                 ▼
          companies.json
                 │
                 ▼
        CompanyInfoAgent
--------------------------------------------------------------------------

Core Workflow

1. User provides organization number
                ↓
2. Application searches the dataset
                ↓
3. Matching company is identified
                ↓
4. Company facts are displayed
                ↓
5. Source URL is provided
                ↓
6. User can verify the record
---------------------------------------------------------------------------------

Complete Project Architecture

                    ┌───────────────┐
                    │     USER      │
                    └───────┬───────┘
                            │
                            ▼
                ┌──────────────────────┐
                │ Organization Number  │
                │       Input          │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │  CompanyInfoAgent    │
                │   Search / Lookup    │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │    companies.json    │
                │ Structured Dataset   │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │ Matching Company     │
                │      Record          │
                └──────────┬───────────┘
                           │
                 ┌─────────┴─────────┐
                 │                   │
                 ▼                   ▼
        ┌────────────────┐   ┌────────────────┐
        │ Company Facts  │   │   Source URL   │
        └────────┬───────┘   └────────┬───────┘
                 │                    │
                 └──────────┬─────────┘
                            ▼
                   ┌────────────────┐
                   │  Verification  │
                   └───────┬────────┘
                           │
                           ▼
                   ┌────────────────┐
                   │  User Result   │
                   └────────────────┘
---------------------------------------------------------

Project Summary

       🔢 Organization Number
                 │
                 ▼
       🔎 CompanyInfoAgent
                 │
                 ▼
       🏢 Company Information
                 │
                 ▼
          🔗 Source Evidence
                 │
                 ▼
          ✅ Verification

---------------------------------------------------

Built With

HTML5
CSS3
JavaScript
JSON
Brønnøysund Register Centre Data
----------------------------------------------------

 👥 Team

Team Leader: Vikash Kasaudhan

Role: Team Leader & Frontend Developer







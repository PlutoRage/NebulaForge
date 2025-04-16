# NebulaForge

A fully automated cloud-native data pipeline built with Python, AWS S3, Glue, and Athena.  
NebulaForge pulls live weather data from OpenWeatherMap, stores it in Amazon S3, catalogs it with AWS Glue, and makes it queryable with SQL via Athena — all without managing any servers.

---

## Features

- Pulls real-time weather data from multiple cities using Python
- Stores structured `.csv` data in an Amazon S3 bucket
- Uses AWS Glue to automatically catalog the data schema
- Enables fast querying with AWS Athena
- Designed to scale and be dashboard-ready

---

## Stack

| Tech                  | Role                             |
|-----------------------|----------------------------------|
| Python                | Data collection + automation     |
| pandas                | Data structuring                 |
| OpenWeatherMap API    | Real-time data source            |
| AWS S3                | Cloud object storage             |
| AWS Glue              | Schema discovery and cataloging  |
| AWS Athena            | Serverless SQL querying          |
| .env                  | Secure API key storage           |

---

## Example Output (Athena Query)

| city      | temp_c | humidity | pressure | weather         | timestamp                        |
|-----------|--------|----------|----------|------------------|----------------------------------|
| Boston    | 10.81  | 45       | 1002     | broken clouds    | 2025-04-16T16:30:36.955637       |
| New York  | 10.42  | 43       | 1008     | overcast clouds  | 2025-04-16T16:30:36.992640       |

---

## How It Works

1. Python pulls live weather data via OpenWeatherMap API  
2. Data is saved as `weather_data.csv` in the `/data` folder  
3. File is uploaded to Amazon S3  
4. AWS Glue crawler detects schema and stores metadata in the Glue Data Catalog  
5. AWS Athena reads the file from S3 and makes it queryable using SQL  

---

## Project Structure

```
NebulaForge/
├── data/               # Local data output
├── scripts/            # Python scripts
│   └── weather_pull.py
├── terraform/          # (optional future deployment)
├── venv/               # Virtual environment
├── .env                # API keys and secrets
└── README.md           # Project documentation
```

---

## What I Learned

- How to integrate Python with cloud data tools
- How to structure S3 buckets and Glue crawlers for Athena
- Troubleshooting quote parsing, encoding, and line breaks in real-world data
- Building a reusable, serverless data pipeline with minimal infrastructure

---

## Future Enhancements

- Schedule the pipeline with AWS Lambda + CloudWatch Events
- Visualize data in Streamlit or QuickSight
- Add unit tests and CI/CD to the repo
- Add support for more cities or weather providers

---

## Screenshots

### Athena Query Result

![Athena Output](https://user-images.githubusercontent.com/your-image-path.png)

---



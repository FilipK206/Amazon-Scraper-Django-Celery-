# **Amazon Scraper**

A Django-based web scraping application that extracts product data from Amazon using BeautifulSoup, schedules periodic scraping tasks with Celery and Redis, and stores the data in an SQLite database. 

This project includes features for creating and managing products, logging scraping events, and scheduling regular scraping tasks.

---

## **Features**
- Scrape product data (e.g., title, price, metadata) from Amazon.
- Manage product information using a Django admin panel.
- Log and store each scraping event for traceability.
- Schedule periodic scraping using Celery and Redis.
- Support for dynamic task scheduling with Celery Beat.

---

## **Technologies Used**
- **Django**: Web framework for backend development.
- **Celery**: Asynchronous task queue for scheduling and executing scraping tasks.
- **Redis**: Message broker for Celery.
- **BeautifulSoup**: Library for parsing and extracting data from web pages.
- **SQLite**: Lightweight database for storing scraped data and logs.

---
## **How It Works**
- **Scrape Data**: The application uses BeautifulSoup to parse product pages from Amazon and extract data like title, price, and metadata.
- **Store Data**: The scraped data is stored in the Product model, and each scraping event is logged in the ProductScrapeEvent model.
- **Schedule Tasks**: Celery Beat is used to schedule periodic scraping tasks. Tasks are queued using Redis and executed asynchronously by Celery workers.
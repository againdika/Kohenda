# Kohenda (GrocerySmart)

Kohenda is an intelligent FMCG price comparison engine and AI dietary lifestyle companion tailored for Sri Lankan retail consumers. The platform crawls, normalizes, and compares real-time grocery prices across leading national supermarket chains (Keells Super and Cargills Food City), while using Retrieval-Augmented Generation (RAG) with Google Gemini AI to synthesize cost-bounded meal plans and calculate lowest-cost shopping baskets.

The project features a native Android mobile client connected to an asynchronous FastAPI backend service, an automated Playwright headless web crawling engine, and a scalable MongoDB Atlas NoSQL cluster.

---

## Architecture Overview

<img width="944" height="661" alt="image" src="https://github.com/user-attachments/assets/c5fab6a3-8323-46e3-9066-9e53f2e4381a" />

---

## Core System Modules

### 1. Mobile Client (Android Application)
* **Real-Time Cross-Retailer Price Comparison:** Displays live supermarket products with visual badges indicating which chain is cheaper and calculating the exact savings delta.
* **AI Smart Lifestyle Companion:** Synthesizes structured, nutritionist-grade meal plans tailored to specific goals (e.g., High Protein, Keto, Weight Loss) strictly bounded by a user-defined budget ceiling in LKR.
* **Supermarket Basket Optimization:** Evaluates required recipe ingredients across both supermarkets and declares the cheaper store for the entire ingredient basket.
* **Geolocation & Store Navigation:** Integrates Google Maps SDK with runtime GPS permissions to render store markers and trigger turn-by-turn directions.
* **Network & Validation Guardrails:** Includes client-side threshold validation and 60-second OkHttp read timeouts with user-friendly alert dialogs for slow network connections.

### 2. Backend & Scraping Engine (Python / FastAPI)
* **High-Throughput Asynchronous Server:** Built with FastAPI and Uvicorn to handle JSON serialization and concurrent mobile client requests.
* **Dynamic Single-Page Application (SPA) Scraping:** Uses Microsoft Playwright to execute headless Chromium instances, navigating JavaScript-rendered storefronts to extract live prices and stock states.
* **24-Hour Synchronization Daemon:** Employs an automated background scheduler that updates price history and monitors market price trends.
* **Web Admin Portal:** Jinja2-rendered management interface for adding products, configuring direct store scraping URLs, uploading assets via Cloudinary, and initiating batch scraping tasks.

---
---

## Technology Stack

| Layer | Technologies Used |
| :--- | :--- |
| **Mobile Client** | Native Android (Java 11), Android SDK, Retrofit 2, OkHttp 3, Google Maps SDK, Material Design Components |
| **Backend Framework** | FastAPI (Python 3.11+), Uvicorn ASGI Server, Pydantic Data Validation, Jinja2 Templates |
| **Artificial Intelligence** | Google GenAI Python SDK, Gemini 2.5 Flash Engine (Pure Structured JSON Mode) |
| **Automation & Scraping**| Microsoft Playwright (Headless Chromium Engine), Asyncio Task Queues |
| **Database & Media** | MongoDB Atlas (Cloud NoSQL), Cloudinary Image CDN |

---

## Setup & Installation Guide

### Prerequisites

* Python 3.11 or higher
* Node.js & npm (required for Playwright browser dependencies)
* Android Studio (Ladybug or newer)
* Active MongoDB Atlas Cluster
* Cloudinary Developer Account
* Google AI Studio API Key

---
Set up a Python virtual environment:
 Contact me
---
Configure Environment Variables:
 Contact Me
---
Android Client Setup
Launch Android Studio and open the GrocerySmart folder.

Open app/src/main/java/com/grocerysmart/network/RetrofitClient.java and confirm the BASE_URL matches your local or deployed backend environment:

Android Emulator: http://10.0.2.2:8000/

Physical Device: http://<YOUR_LOCAL_MACHINE_IP>:8000/

Cloud Instance (AWS/Azure): https://api.yourdomain.com/

Configure your Google Maps API Key in app/src/main/AndroidManifest.xml:

<meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="YOUR_GOOGLE_MAPS_SDK_KEY" />
---

API Reference, Admin Management Endpoints, Security Best Practices:
 Contact me
---
License
This repository is maintained for academic and software engineering research. All product names, retailer logos, and trademarks belong to their respective corporate owners.

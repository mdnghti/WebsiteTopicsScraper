# 🕵️‍♂️ Smart Business & Contact Scraper

A professional, high-performance asynchronous tool for **Lead Generation** and **Business Intelligence**.  
It bypasses modern bot protections (such as Cloudflare) and uses a **local LLM (Ollama)** to intelligently categorize website niches based on their content.

---

# 🚀 Key Features

## Multi-Stage Fetching Pipeline

### Tier 1 — aiohttp
Ultra-fast raw HTML fetching for unprotected websites.

### Tier 2 — cloudscraper
Specialized bypass for Cloudflare TLS fingerprinting protection.

### Tier 3 — Playwright (Stealth)
Full browser emulation to solve JavaScript challenges and decode protected emails.

---

## 🤖 AI-Powered Categorization

Integrated with **Ollama (local LLM)** to analyze website text and automatically determine the business niche.

Examples of detected niches:
- Marketing Agency
- E-commerce
- SaaS
- Consulting
- Software Development

---

## 📧 Smart Contact Extraction

The scraper prioritizes **high-value business emails** over generic ones.

High priority:
- `ceo@`
- `advertising@`
- `partnership@`
- `business@`

Lower priority:
- `info@`
- `office@`
- `support@`

---

## ⚙️ Industrial-Grade Stability

### DNS Pre-check
Quickly skips dead or unreachable domains.

### Batch Processing
Periodically refreshes browser contexts to prevent memory leaks.

### Heartbeat Monitor
Detects stalled tasks and cancels them so the scraper never hangs.

---

# 🛠 Installation Guide

Follow these steps to install and run the scraper on **Windows, Linux, or macOS**.

---

# 1. Prerequisites

Make sure you have installed:

- **Python 3.9+**
- **Ollama**
- **Microsoft Excel** (to prepare input and view results)

---

# 2. Setup Environment & Libraries

It is recommended to use a **virtual environment**.

Create the environment:


python -m venv venv

Activate it.

Linux / macOS:

source venv/bin/activate

Windows:

venv\Scripts\activate

Install required Python libraries:

pip install asyncio aiohttp pandas beautifulsoup4 playwright cloudscraper openai openpyxl
3. Install Playwright Browser

The scraper requires Chromium to handle JavaScript-protected websites.

Install the browser with:

python -m playwright install chromium

This downloads a local Chromium instance used by Playwright.

4. Configure Ollama (Local LLM)

Download Ollama from:

https://ollama.com

Install and launch the application.

Pull the language model used by the scraper (example: Llama 3):

ollama pull llama3

Ensure the Ollama service is running before starting the scraper.

The API endpoint used by the script:

http://localhost:11434/v1
📖 How to Use
1. Prepare Input File

Create an Excel file named:

sites_to_check.xlsx

The file must contain a column named:

URL

Example:

URL
example.com
shop.com
agency.com
2. Run the Scraper

Run the script from the project folder:

python main.py
3. Check Results

After the scraper finishes, results will be saved to:

leads_result.xlsx

The output file contains:

Website URL

Extracted emails

AI-detected business niche

Processing status

🔍 Troubleshooting
Issue	Solution
ModuleNotFoundError	Run pip install [module_name]
Playwright Error	Run python -m playwright install chromium
Ollama Connection Error	Ensure the Ollama application is running
High Memory Usage	Reduce SCRAPER_CONCURRENCY
⚙️ Advanced Configuration

You can configure performance using environment variables.

SCRAPER_CONCURRENCY

Number of websites processed simultaneously.

Default value:

2

Example:

Linux / macOS:

export SCRAPER_CONCURRENCY=5

Windows:

set SCRAPER_CONCURRENCY=5
OPENAI_BASE_URL

API endpoint used for Ollama.

Default value:

http://localhost:11434/v1
📊 Output

The scraper generates the file:

leads_result.xlsx

It includes:

Website URL

Extracted contact emails

AI-detected niche

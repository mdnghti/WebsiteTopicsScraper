# 🕵️‍♂️ Smart Business & Contact Scraper

A professional, high-performance asynchronous tool for **Lead Generation** and **Business Intelligence**.  
It bypasses modern bot protections (like Cloudflare) and uses a **local LLM (Ollama)** to intelligently categorize website niches based on their content.

---

# 🚀 Key Features

## Multi-Stage Fetching Pipeline

**Tier 1: aiohttp**  
Ultra-fast raw HTML fetching for unprotected sites.

**Tier 2: cloudscraper**  
Specialized bypass for Cloudflare TLS fingerprinting.

**Tier 3: Playwright (Stealth)**  
Full browser emulation to solve JavaScript challenges and decode protected emails.

---

## AI-Powered Categorization

Integrated with **Ollama (local LLM)** to analyze website text and automatically determine the business niche.

Examples:
- Marketing Agency
- E-commerce
- SaaS

---

## Smart Contact Extraction

Prioritizes **high-value business emails** over generic ones.

High priority:
- `ceo@`
- `advertising@`
- `partnership@`

Low priority:
- `info@`
- `office@`

---

## Industrial-Grade Stability

**DNS Pre-check**  
Quickly skips dead or unreachable domains.

**Batch Processing**  
Periodically refreshes browser contexts to prevent memory leaks.

**Heartbeat Monitor**  
Detects and cancels stalled tasks so the scraper never hangs.

---

# 🛠 Installation Guide

Follow these steps to set up the environment on **Windows, Linux, or macOS**.

---

# 1. Prerequisites

- Python **3.9+**
- **Ollama** (installed and running)
- **Excel** (to prepare input and view results)

---

# 2. Setup Environment & Libraries

It is recommended to use a **virtual environment**.

```bash
# Create and activate virtual environment
python -m venv venv

# Linux / macOS
source venv/bin/activate

# Windows
venv\Scripts\activate

# Install Python dependencies
pip install asyncio aiohttp pandas beautifulsoup4 playwright cloudscraper openai openpyxl

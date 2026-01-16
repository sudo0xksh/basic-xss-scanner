# 🧪 Basic XSS Scanner

Basic XSS Scanner is a Python-based CLI tool that scans web pages for
reflected Cross-Site Scripting (XSS) vulnerabilities by testing HTML forms
with common payloads.

It is designed for learning purposes and demonstrates how XSS testing
works at a basic level.

---

## Overview

Cross-Site Scripting often occurs through vulnerable form inputs.

This tool:
- Fetches a webpage
- Extracts all HTML forms
- Injects common XSS payloads into form fields
- Checks server responses for payload reflection

If a payload appears in the response, it flags a potential XSS issue.

---

## Features

- Scans a single URL or multiple URLs from a file
- Automatically extracts forms and input fields
- Tests multiple common XSS payloads
- Supports GET and POST form methods
- Prints results directly to the terminal
- Saves confirmed findings to a report file

---

## How It Works

The scanner requests the target page and parses its HTML using BeautifulSoup.

For each form found:
- The form action and method are identified
- Each input field is populated with XSS payloads
- Requests are sent using GET or POST
- Responses are checked for reflected payloads

When a payload is detected in the response, the issue is reported and logged.

---

## Usage

To scan a single URL  
python xss_scanner.py -u <url>

To scan multiple URLs from a file  
python xss_scanner.py -l <input.txt>

Each URL in the file should be on a new line.

---

## Output

The tool displays:
- Target URL
- Number of forms found
- Form action and method
- Detected XSS payloads and affected parameters

Confirmed findings are saved to a file named `xss_report.txt`.

---

## Requirements

- Python 3.x
- requests library
- beautifulsoup4 library

Install dependencies if needed  
pip install requests beautifulsoup4

---

## Notes

- This scanner checks only for basic reflected XSS
- Payloads are intentionally loud and simple
- False positives are possible
- Intended strictly for learning and authorized testing

---

## Final Thoughts

Understanding XSS starts with understanding how forms handle input.
This tool helps build that understanding step by step.

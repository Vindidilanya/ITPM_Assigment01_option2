# Image Preview Test Automation (Playwright)

Automated test to verify the image preview functionality on [pixelssuite.com/convert-to-png](https://www.pixelssuite.com/convert-to-png) using Playwright.

## Prerequisites

- Python 3.11 or 3.12 (recommended)
- Google Chrome installed (or Playwright will use Chromium)

## Installation

```bash
python -m pip install -U pip
python -m pip install playwright openpyxl
python -m playwright install
```

## Running the Test

```bash
python image_preview_test.py --url "https://www.pixelssuite.com/convert-to-png" --slow-mo-ms 2000
```

### Optional Arguments

| Argument | Default | Description |
|---|---|---|
| `--url` | `https://www.pixelssuite.com/convert-to-png` | Target URL |
| `--png` | `sample.png` | PNG file to upload |
| `--out-dir` | `results` | Folder for screenshots |
| `--csv` | `execution_results.csv` | CSV output file |
| `--headless` | `False` | Run browser in headless mode |
| `--timeout-ms` | `60000` | Timeout in milliseconds |
| `--slow-mo-ms` | `0` | Slow motion delay in milliseconds |

## Results

- `execution_results.csv` — contains test execution results (file type, path, preview detected, status, screenshot path)
- `results/preview_pass.png` — screenshot taken when test passes
- `results/preview_fail.png` — screenshot taken when test fails
- `results/preview_error.png` — screenshot taken on unexpected error

## Test Scenario

**Feature:** Image Format Conversion (Convert to PNG)  
**Type:** Positive test case  
**Steps:**
1. Navigate to `https://www.pixelssuite.com/convert-to-png`
2. Upload a valid PNG image file
3. Verify that a preview of the uploaded image is displayed on the page

**Expected Result:** Preview section is visible with the uploaded image  
**Status:** PASS

# Instagram Scraper for UPSC Influencer Identification

## Overview

This project consists of two Python scripts designed to automate the process of identifying potential social media influencers on Instagram within the UPSC (Union Public Service Commission) examination domain.  It scrapes user data based on relevant hashtags and then analyzes user profiles to filter for those with a significant focus on UPSC-related content and a substantial follower base.

## Project Structure

The project contains the following files:

* `instagram_scraper_part1.py`: This script scrapes Instagram for usernames based on a list of hashtags.
* `instagram_scraper_part2.py`: This script takes the usernames collected by `part1` and analyzes their profiles to identify potential UPSC influencers.
* `usernames_partial.txt`: (Intermediate) A temporary file used to store the usernames collected by `part1` before they are processed by `part2`.
* `upsc_usernames_raw3.txt`: The raw output of the first script.
* `upsc_verified_accounts.xlsx`: The final output file (Excel format) containing the list of verified UPSC influencers, their follower counts, and profile URLs.
* `README.md`: This file (project documentation).

## Dependencies

Before running the scripts, ensure you have the following dependencies installed:

* **Python 3.6 or higher:** The scripts are written in Python 3.
* **Selenium:** A Python library for controlling web browsers.  Install using `pip install selenium`.
* **undetected-chromedriver:** A modified version of ChromeDriver that helps to avoid detection by anti-bot measures. Install using `pip install undetected-chromedriver`.
* **pandas:** A Python library for data manipulation and analysis (for writing to Excel). Install using `pip install pandas`.

## Setup

1.  **Clone the Repository:** Clone this repository to your local machine using `git clone <repository_url>`.
2.  **Install Dependencies:** Navigate to the project directory and install the required Python packages using `pip install -r requirements.txt` (if you create a `requirements.txt` file) or install them individually as mentioned above.
3.  **ChromeDriver:** `undetected-chromedriver` should handle the ChromeDriver installation automatically.
4.  **Manual Login:** Both scripts require you to log in to your Instagram account manually in a Chrome browser window controlled by Selenium.

## Usage

**Part 1: Scraping Usernames**

1.  Run the `instagram_scraper_part1.py` script: `python instagram_scraper_part1.py`
2.  The script will open a Chrome browser window and navigate to the Instagram login page.
3.  **Manually log in to your Instagram account.**
4.  Once you are logged in, press Enter in your terminal.
5.  The script will then start scraping usernames based on the defined hashtags.
6.  The scraped usernames will be saved in the `usernames_partial.txt` and `upsc_usernames_raw3.txt` files.

**Part 2: Analyzing Profiles and Identifying Influencers**

1.  Ensure that `instagram_scraper_part1.py` has been run successfully and the `usernames_partial.txt` file has been created.
2.  Run the `instagram_scraper_part2.py` script: `python instagram_scraper_part2.py`
3.  The script will open a Chrome browser window and navigate to the Instagram login page.
4.  **Manually log in to the same Instagram account used in Part 1.**
5.  Once you are logged in, press Enter in your terminal.
6.  The script will read the usernames from `usernames_partial.txt`, analyze their profiles, and filter them based on the criteria defined in the script.
7.  The final list of verified UPSC influencers will be saved in the `upsc_verified_accounts.xlsx` file.

## Important Considerations

* **Instagram's Terms of Service:** This script is intended for research and informational purposes only.  Scraping Instagram data may violate their terms of service.  Use this script responsibly and at your own risk.
* **Rate Limiting:** Instagram has rate limits to prevent abuse.  The script includes delays to try to avoid triggering these limits, but you may still encounter issues.  If you do, try reducing the number of `SCROLLS` in `part1` and/or increasing the `time.sleep()` values in both scripts.
* **Account Safety:** Excessive or aggressive scraping can put your Instagram account at risk.  Use this script with caution and consider using a separate, less important account for scraping.
* **Website Changes:** Instagram's website structure can change, which may break the script.  If this happens, you may need to update the CSS selectors and/or XPath expressions in the script.
* **Error Handling:** The scripts include some error handling (e.g., for WebDriver exceptions and general exceptions), but they may not be comprehensive.  Monitor the script's output for any errors and be prepared to debug them.
* **Manual Login:** The scripts require manual login to Instagram. This is a design choice to bypass some anti-bot detection mechanisms.

## Disclaimer

This project is for educational and research purposes only. The authors and contributors are not responsible for any misuse or consequences arising from the use of this script.  Use it responsibly and in compliance with Instagram's terms of service.

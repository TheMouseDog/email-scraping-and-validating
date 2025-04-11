# Project Goal

Gather information such as address and email of a certain type of companies in a certain region. I needed a list of electricians in the region of Flanders (Belgium) so you'll find this as example below. You can change this to your own needs.

The goal of this project is to **gather, clean and validate** information for a certain type of company in a certain region. All of the collected data will be exported to a .csv which can then be imported in an email marketing tool such as Hubspot, Mailchimp ... to start the campaign.

**Notes:**

*  We're following GDPR guidelines, so only public e-mail addresses are scraped. It is crucial to clean our data and validate e-mail addresses to minimize bounce rate and keep our mailbox clean.

* Never use your personal e-mail address to send email marketing campaigns. Never use Outlook. Opt for Mailchimp, HubSpot, or any other specialized tool to send your campaigns. Additionally, ensure you configure DMARC, DKIM, and SPF to prevent your emails from being flagged as spam. See https://www.cloudflare.com/learning/email-security/dmarc-dkim-spf/ for more info.*


## Method

* Gather Data: Use Google Maps Geocoding API to find the companies we're interested in and extract relevant details. Extract to a .csv-file. 

* Clean Data: Remove duplicates, correct any inconsistencies, and format the data appropriately with Pandas (or Excel). Create a separate dataframe for companies containing and not containing e-mail addresses.

* Extract e-mails: Import the .csv-file with the data gathered using the Maps API and scrape e-mail addresses using Requests and BeautifulSoup.

* Fill e-mails: Generate e-mail addresses based on URL for records not containing e-mail addresses. 

* Validate Emails: Check the syntactic and domain validity of the email addresses to ensure they're real. Remove invalid records. Save in a new DF and export to a .csv-file.

* Check the results: Check the final data versus the gathered data to evaluate succes of enriching. **(work in progress)**

* Next steps: Import the final data ("..-emails-filled-validated.csv" and "..-emails-scraped.csv") in your E-mail marketing or CRM tool(s).

      *You will need a Google Cloud account to activate the Geocode API and the Maps Platform API:
        Generate your Google maps API Key and fill in where you encounter `API_KEY = your api key`
        See https://developers.google.com/maps/documentation/maps-static for more information.*

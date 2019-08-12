---
author: "Vignesh Krish"
date: 2019-08-12
linktitle: api wrapper for Ørsted electricity data
title: Electricity Consumption Data - Ørsted API
---

**Disclaimer**: This is an endpoint that has been reverse engineered to get the relevant data. so it might survive for long if Oersted or their IT decides to change their authentication protocol.

Download this to scrape the data from start until the current date: [scrape_data_standalone.py](https://raw.githubusercontent.com/vignkri/heda/master/scrape_data_standalone.py)

Last year, I had a quick post on the data collected from the smart meter installed here in Denmark. Consequently, the energy provider, Oersted, set up an online system where it is easier to see the data. However, the online dashboard masks all the usefulness from the dataset for someone who is interested in analysing it. 

So, after some snooping around and reverse engineering, I was able to pinpoint the queries that power the online personal dashboard. So, based on the dashboard's network options, I was able to reconstruct the authentication requirements and the data endpoints. This enables the following:

1. With the Customer Number (Kundenummer) and the EAN number (Aftagenummer), you'll be able to authenticate the token required for getting the data.
2. You can also use the email-address / password combination to extract the data but you'll need to add that as a JSON payload during authentication instead of the current payload.

This endpoint can be automated by storing last known invocation of the scraper and offsetting the from-date and the to-date. This will allow for the you reconstruct the dataset required for your analysis.

All of the required code can be found at the [HEDA Github Repo](https://github.com/vignkri/heda). 

If you clone the repository, once you have the virtual environment setup, you can use the `scape_data.py` file as a script to download the relevant data points. It currently is setup to get the data from late July to the current date and export them as JSON files.

## Examples 

**Note**: You can also use the email address and password to authenticate, but I did not use that process to log in. So, feel free to change the code to allow for authentication using the email address and password.

### Authentication

Here is a code example for authenticating and setting up the API wrapper to get the relevant data. The key is the required environmental variables from the user:

1. Customer Number (Kundenummer)
2. EANumber or Password (Aftagenummer / Adgangskode)

Both of these data points should be available from either your login credentials on the dashboard. They should also be available if you get the quarterly balance updates / invoices. 

```{python}
customer_number = <user-customer-number>
ean = <user-ean>

# Create an instance of the API
api = OrstedPrivate(customer_no=customer_number, ea_number=ean)

# Authenticate the number by using the authenticate method
api.authenticate()
```

### Hourly Data

After authentication, the hourly data can be extracted. There is a limit on the number of days for which you can extract hourly data. The `scrape_data.py` file automatically sets it to 1 week. The limit is approximately 2 weeks in case you are building your own looping mechanism.

```{python}

# Date formats are YYYY-MM-DD

from_date = '2019-01-01'
to_date = '2019-01-23'

# Get the data using the api instance
result = api.get_hourly(from_date=from_date,
                        to_date=to_date)
```

This should output a straightforward JSON file if the query succeeds. If the query doesn't succeed, you'll need to check whether the authentication passed.


**Notes**

- I've used [Arrow](https://arrow.readthedocs.io/en/latest/) as the timestamp generating library instead of the builtin `datetime` module for practice purposes.
- This is a bulk downloading script, so it gets all the data and dumps as JSON to disk but feel free to use the script for download precisely on certain days.
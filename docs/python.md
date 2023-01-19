# Python
Hawqal is a standalone python package having the data of world’s countries, states, and their cities. One of its own kind of python library having the metropolitan data at such a large scale. Now it’s easy for the end-user to get the required data by just calling the relevant functions instead of collecting data manually and looping over a data structure to store and retrieve. Returned data will be of Json format

To install the package in Python, run the following command:

### Installation
```
 pip install hawqal
```
### Functions
- `getCountries()`
- `getStates()`
- `getCities()`
- `getCountry()`
- `getState()`
- `getCity()`
### Filters
By default all the Filters are set to `False`. If certain value is not required
set that filter to `True`

|   Country Filter      |State Filter   |City Filter
|----------             |----------     |----------
|country_name           |state_id       |city_id
|iso_code               |state_name     |city_name
|phone_code             |country_name     |state_name
|capital                |longitude      |state_id
|currency               |latitude       |country_name
|currency_name          |               |longitude
|currency_symbol        |               |latitude
|region
|subregion
|country_domain
|time_zone
|zone_city
|UTC
|longitude
|latitude
    
# Usage/Example
## Countries
- #### Countries
    ```Python
     >>> hawqal.getCountries()
    
     [
        {
            "country_name": "Afghanistan",
            "iso_code": "AFG",
            "phone_code": "+93",
            "capital": "Kabul",
            "currency": "AFN",
            "currency_name": "Afghan afghani",
            "currency_symbol": "؋",
            "country_domain": ".af",
            "region": "Asia",
            "subregion": "Southern Asia",
            "timezone": "Asia ",
            "zone_city":" Kabul  ",
            "UTC": " 04:30  ",
            "latitude": "33",
            "longitude": "65"
         }, 
         {
            "country_name": "Aland Islands",
            "iso_code": "ALA", 
            "phone_code": "+340", 
            "capital": "Mariehamn", 
            "currency": "EUR", 
            "currency_name": "Euro", 
            "currency_symbol": "€", 
            "country_domain": ".ax", 
            "region": "Europe", 
            "subregion": "Northern Europe", 
            "timezone": "Europe ",
            "zone_city": " Mariehamn  ",
            "UTC": " 02:00  ",
            "latitude": "60.116667",
            "longitude": "19.9"
            },
            ...
     ]
    ```
   
- #### Countries with Filters
    ```Python
    >>> hawqal.getCountries(filter=hawqal.CountryFilter(iso_code=True,latitude=True,longitude=True))
    
    [
        {
            "iso_code": "AFG", 
            "longitude": "65", 
            "latitude": "33"
        },
        {
            "iso_code": "ALA",
            "longitude": "19.9",
            "latitude": "60.116667"
        },
        {
            "iso_code": "ALB", 
            "longitude": "20", 
            "latitude": "41"
        },
        ...
    ]
    ```
    
- #### Single Country with Filters
    ```Python
    >>> hawqal.getCountry(country_name="pakistan",filter=hawqal.CountryFilter(currency=True,currency_name=True,country_name=True))
    
    [
        {
            "country_name": "Pakistan",
            "currency": "PKR",
            "currency_name": "Pakistani rupee"
        }
    ]
    ```

- #### Single Country
  ```Python
  >>> hawqal.getCountry(country_name="pakistan")

  [
    {
      "country_name": "Pakistan",
      "iso_code": "PAK",
      "phone_code": "+92",
      "capital": "Islamabad",
      "currency": "PKR",
      "currency_name": "Pakistani rupee",
      "currency_symbol": "₨",
      "country_domain": ".pk",
      "region": "Asia",
      "subregion": "Southern Asia",
      "timezone": "Asia",
      "zone_city": "Karachi",
      "UTC": "05:00",
      "latitude": "30",
      "longitude": "70"
    }
  ]
  ```
    
## State
- #### States
    ```Python
    >>> hawqal.getStates()
    
    [
        {
            "state_id": 3901,
            "state_name": "Badakhshan", 
            "country_name": "Afghanistan", 
            "latitude": "36.7347725", 
            "longitude": "70.8119953"
        },
        {
            "state_id": 3871,
            "state_name": "Badghis",
            "country_name": "Afghanistan",
            "latitude": "35.1671339",
            "longitude": "63.7695384"
        },
        ...
    ]
    ```
    
- #### States by Country
    ```Python
    >>> hawqal.getStates("pakistan")
    
    [
        {
            "state_id": 3172,
            "state_name": "Azad Kashmir", 
            "country_name": "Pakistan", 
            "latitude": "33.9259055", 
            "longitude": "73.7810334"
        },
        {
            "state_id": 3174, 
            "state_name": "Balochistan", 
            "country_name": "Pakistan", 
            "latitude": "28.4907332", 
            "longitude": "65.0957792"
        },
        ...
    ]
    ```
    
- #### Single State
    ```Python
    >>> hawqal.getState(country_name="pakistan", state_name="sindh")
   
    [
         {
             "state_id": 3175,
             "state_name": "Sindh",
             "country_name": "Pakistan", 
             "latitude": "25.8943018", 
             "longitude": "68.5247149"
        }
     ]
    ```
   
- #### Single State with Filters
    ```Python
    >>> hawqal.getState(country_name="pakistan",  state_name="sindh",  filter=hawqal.StateFilter(state_id=False,latitude=True, longitude=True,country_name=True))
    
    [
         {
             "country_name": "Pakistan",
             "longitude": "68.5247149",
             "latitude": "25.8943018"
         }
     ]
    ```
   
## Cities
- #### Cities
    ```Python
    >>> hawqal.getCities()
    
    [
        {
            "city_id": 52,
            "city_name": "Ashkāsham",
            "state_name": "Badakhshan", 
            "state_id": 3901, 
            "country_name": "Afghanistan", 
            "latitude": "36.68333", 
            "longitude": "71.53333"
        }, 
        {
            "city_id": 68, 
            "city_name": "Fayzabad", 
            "state_name": "Badakhshan",
            "state_id": 3901, 
            "country_name": "Afghanistan", 
            "latitude": "37.11664", 
            "longitude": "70.58002"
        },
        ...
    ]
    ```
    
- #### Cities by Country
    ```Python
    >>> hawqal.getCities(country_name='pakistan')
    
    [
        {
            "city_id": 85368,
            "city_name": "Bhimbar", 
            "state_name": "Azad Kashmir", 
            "state_id": 3172, 
            "country_name": "Pakistan", 
            "latitude": "32.97465", 
            "longitude": "74.07846"
        }, 
        {
            "city_id": 85562, 
            "city_name": "Kotli", 
            "state_name": "Azad Kashmir", 
            "state_id": 3172, 
            "country_name": "Pakistan", 
            "latitude": "33.51836", 
            "longitude": "73.9022"
        },
        ...
    ]
    ```
   
- #### Cities by Country and State
    ```Python
    >>> hawqal.getCities(country_name="pakistan", state_name="punjab")
    
    [
         {
             "city_id": 85332, 
             "city_name": "Ahmadpur Sial", 
             "state_name": "Punjab", 
             "state_id": 3176, 
             "country_name": "Pakistan", 
             "latitude": "30.67791", 
             "longitude": "71.74344"
        },
        {
            "city_id": 85331,
            "city_name": "Ahmedpur East",
            "state_name": "Punjab",
            "state_id": 3176,
            "country_name": "Pakistan",
            "latitude": "29.14269", 
            "longitude": "71.25771"
        },
        ...
     ] 
    ```
    
- #### Cities with Filters
    ```Python
    >>> hawqal.getCities(country_name="pakistan",  state_name="punjab",  filter=hawqal.CityFilter(latitude=True,city_name=True))
    
    [
        {
            "city_name": "Ahmadpur Sial",
            "latitude": "30.67791"
        },
        {
            "city_name": "Ahmedpur East",
            "latitude": "29.14269"
        }, 
        {
            "city_name": "Alipur Chatha", 
            "latitude": "29.38242"
        },
        ...
    ]
    ```
    
- #### Single City
    ```Python
    >>> hawqal.getCity(city_name="wah")
    
    [
        {
            "city_id": 143779,
            "city_name": "Wah",
            "state_name": "Punjab",
            "state_id": 3176,
            "country_name": "Pakistan",
            "latitude": "33.81",
            "longitude": "72.70972222"
        }
    ]
    ```
    

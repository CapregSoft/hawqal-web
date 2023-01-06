# Python
To install the package in Python, run the following command:
### Installation
- windows
  ```python
  pip install hawqal
  ```
- macos/linux
  ```python
  pip3 install hawqal
  ```
- Latest version
  ```python
  pip install --upgrade hawqal
  ```
### Functions
- `getCountry()`
- `getCountries()`
- `getCity()`
- `getCities()`
- `getState()`
- `getStates()`
### Filters
By default all Filters are set to `True`. If certain value is not required
set that filter to `False`
- CountryFilter
    |   Filter      | Filter        |Filter
    |----------     |----------     |----------
    |country_name   |currency_name  |zone_city
    |iso_code       |currency_symbol|country_domain
    |phone_code     |region         |longitude
    |capital        |subregion      |latitude
    |currency       |time_zone      |UTC
- StateFilter
    |   Filter      | Filter     |Filter
    |----------     |----------  |------
    |country_name   |state_name  |longitude
    |state_id       |latitude
- CityFilter
    |   Filter      | Filter     |Filter
    |----------     |----------  |---------
    |city_id        |country_name|latitude
    |city_name      |state_id    |longitude
    |state_name     |
# Usage/Example
## Countries Module
- #### Returns Countries along with Filters
    ```python
    hawqal.getCountries()
    ```
- Success Response
  ```python
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
        "zone_city": " Kabul  ",
        "UTC": " 04:30  ",
        "longitude": "65",
        "latitude": "33"
    },...
  ]
  ```
  - #### Returns Countries with Selected Filters
  ```python
    hawqal.getCountries(filter=hawqal.CountryFilter(iso_code=False,latitude=False,longitude=False))
  ```
- Success Response
  ```python
  [
    {
        "country_name": "Afghanistan",
        "phone_code": "+93",
        "capital": "Kabul",
        "currency": "AFN",
        "currency_name": "Afghan afghani",
        "currency_symbol": "؋",
        "country_domain": ".af",
        "region": "Asia",
        "subregion": "Southern Asia",
        "timezone": "Asia ",
        "zone_city": " Kabul  ",
        "UTC": " 04:30  "
    },...
  ]
  ```
- #### Returns single Country data
    ```python
    hawqal.getCountry(country_name="pakistan",  filter=hawqal.CountryFilter(iso_code=False,latitude=False,longitude=False,currency=False,currency_name=False))
    ```
- Success Response
  ```python
  [
    {
        "country_name": "Pakistan",
        "phone_code": "+92",
        "capital": "Islamabad",
        "currency_symbol": "₨",
        "country_domain": ".pk",
        "region": "Asia",
        "subregion": "Southern Asia",
        "timezone": "Asia ",
        "zone_city": " Karachi  ",
        "UTC": " 05:00  "
    }
  ]
  ```
## States Module
- #### Returns States along with Filters
    ```python
    hawqal.getStates()
    ```
- Success Response
    ```python
    [
        {
            "state_id": 3901,
            "state_name": "Badakhshan",
            "country_name": "Afghanistan",
            "longitude": "70.8119953",
            "latitude": "36.7347725"
        },
        {
            "state_id": 3871,
            "state_name": "Badghis",
            "country_name": "Afghanistan",
            "longitude": "63.7695384",
            "latitude": "35.1671339"
        },...
    ]
    ```
- #### Returns States of single country
    ```python
    hawqal.getStates("pakistan")
    ```
- Success Response
    ```python
    [
        {
            "state_id": 3172,
            "state_name": "Azad Kashmir",
            "country_name": "Pakistan",
            "longitude": "73.7810334",
            "latitude": "33.9259055"
        },
        {
            "state_id": 3174,
            "state_name": "Balochistan",
            "country_name": "Pakistan",
            "longitude": "65.0957792",
            "latitude": "28.4907332"
        },...
    ]
    ```
- #### Returns Single State
    ```python
    hawqal.getState(country_name="pakistan", state_name="punjab")
    ```
- Success Response
    ```python
    [
        {
            "state_id": 3176,
            "state_name": "Punjab",
            "country_name": "Pakistan",
            "longitude": "75.3412179",
            "latitude": "31.1471305"
        }
    ]
    ```
- #### Returns Single State with Filters
    ```python
    hawqal.getState(country_name="pakistan",  state_name="punjab",  filter=hawqal.StateFilter(
    latitude=False, longitude=False))
    ```
- Success Response
    ```python
    [
        {
            "state_id": 3176,
            "state_name": "Punjab",
            "country_name": "Pakistan"
        }
    ]
    ```
## City Module
- #### Returns Cities along with Filters
    ```python
    hawqal.getCities()
    ```
- Success Response
    ```python
    [
        {
            "country_name": "Afghanistan", 
            "city_id": 52, 
            "city_name": "Ashkāsham", 
            "state_id": 3901, 
            "state_name": "Badakhshan", 
            "latitude": "36.68333", 
            "longitude": "71.53333"
        }, 
        {
            "country_name": "Afghanistan", 
            "city_id": 68, 
            "city_name": "Fayzabad", 
            "state_id": 3901, 
            "state_name": "Badakhshan", 
            "latitude": "37.11664", 
            "longitude": "70.58002"
        },...
    ] 
    ```
- #### Returns Cities of a Country
    ```python
    hawqal.getCities(country_name='pakistan')
    ```
- Success Response
    ```python
    [
        {
            "country_name": "Pakistan",
            "city_id": 85368,
            "city_name": "Bhimbar",
            "state_id": 3172,
            "state_name": "Azad Kashmir",
            "latitude": "32.97465",
            "longitude": "74.07846"
        },
        {
            "country_name": "Pakistan",
            "city_id": 85562,
            "city_name": "Kotli",
            "state_id": 3172,
            "state_name": "Azad Kashmir",
            "latitude": "33.51836",
            "longitude": "73.9022"
        },...
    ]
    ```
- #### Return Cities by Country and State
    ```python
    hawqal.getCities(country_name="pakistan", state_name="punjab")
    ```
- Success Response
    ```python
    [
        {
            "state_id": 3176,
            "state_name": "Punjab",
            "country_name": "Pakistan",
            "longitude": "75.3412179",
            "latitude": "31.1471305"
        }
    ]
    ```
- #### Return Cities with Filters
    ```python
    hawqal.getCities(country_name="pakistan",  state_name="punjab",  filter=hawqal.CityFilter(
    latitude=False))
    ```
- Success Response
    ```python
    [
        {
            "country_name": "Pakistan",
            "city_id": 85332,
            "city_name": "Ahmadpur Sial",
            "state_id": 3176,
            "state_name": "Punjab",
            "longitude": "71.74344"
        },
        {
            "country_name": "Pakistan",
            "city_id": 85331,
            "city_name": "Ahmedpur East",
            "state_id": 3176,
            "state_name": "Punjab",
            "longitude": "71.25771"
        },...
    ]
    ```
- #### Returns Single City along with Filters
    ```python
    hawqal.getCity(city_name="wah")
    ```
- Success Response
    ```python
    [
        {
            "country_name": "Pakistan",
            "city_id": 143779,
            "city_name": "Wah",
            "state_id": 3176,
            "state_name": "Punjab",
            "latitude": "33.81",
            "longitude": "72.70972222"
        }
    ]
    ```
- #### Returns Single City with Filters
    ```python
    hawqal.getCity(country_name="pakistan",state_name="punjab",city_name="wah",filters=hawqal.CityFilter(latitude=False))
    ```
- Success Response
    ```python
    [
        {
            "country_name": "Pakistan",
            "city_id": 143779,
            "city_name": "Wah",
            "state_id": 3176,
            "state_name": "Punjab",
            "longitude": "72.70972222"
        }
    ]
    ```

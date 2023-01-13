# Python
Hawqal is a standalone python package having the data of world’s countries, states, and their cities. One of its own kind of python library having the metropolitan data at such a large scale. Now it’s easy for the end-user to get the required data by just calling the relevant functions instead of collecting data manually and looping over a data structure to store and retrieve. Returned data will be of Json format

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
- `getCountries()`
- `getStates()`
- `getCities()`
- `getCountry()`
- `getState()`
- `getCity()`
### Filters
By default all the Filters are set to `True`. If certain value is not required
set that filter to `False`

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
- #### Returns Countries along with Filters
    ```python
    hawqal.getCountries()
    ```
    - #### Success Response
       ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/11.PNG)
- #### Returns Countries with Selected Filters
    ```python
    hawqal.getCountries(filter=hawqal.CountryFilter(iso_code=False,latitude=False,longitude=False))
    ```
    - #### Success Response
        ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/22.PNG)
- #### Returns single Country data
    ```python
    hawqal.getCountry(country_name="pakistan",  filter=hawqal.CountryFilter(currency=False,currency_name=False))
    ```
    - #### Success Response
        ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/33.PNG)
## State
- #### Returns States along with Filters
    ```python
    hawqal.getStates()
    ```
    - #### Success Response
        ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/44.PNG)
- #### Returns States of single country
    ```python
    hawqal.getStates("pakistan")
    ```
    - #### Success Response
        ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/55.PNG)
- #### Returns Single State
    ```python
    hawqal.getState(country_name="pakistan", state_name="sindh")
    ```
    - #### Success Response
        ![](https://github.com/CapregSoft/Hawqal-python/blob/hawqal-to-json/screenshots/66.PNG?raw=true)
- #### Returns Single State with Filters
    ```python
    hawqal.getState(country_name="pakistan",  state_name="sindh",  filter=hawqal.StateFilter(state_id=False
    latitude=False, longitude=False))
    ```
    - #### Success Response
        ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/77.PNG)
## Cities
- #### Returns Cities along with Filters
    ```python
    hawqal.getCities()
    ```
    - #### Success Response
        ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/99.PNG)
- #### Returns Cities of a Country
    ```python
    hawqal.getCities(country_name='pakistan')
    ```
    - #### Success Response
        ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/100.PNG)
- #### Returns Cities by Country and State
    ```python
    hawqal.getCities(country_name="pakistan", state_name="punjab")
    ```
    - #### Success Response
        ![](https://github.com/CapregSoft/Hawqal-python/blob/hawqal-to-json/screenshots/102.PNG?raw=true)
- #### Returns Cities with Filters
    ```python
    hawqal.getCities(country_name="pakistan",  state_name="punjab",  filter=hawqal.CityFilter(
    latitude=False))
    ```
    - #### Success Response
        ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/101.PNG)
- #### Returns Single City along with Filters
    ```python
    hawqal.getCity(city_name="wah")
    ```
    - #### Success Response
        ![](https://raw.githubusercontent.com/CapregSoft/Hawqal-python/hawqal-to-json/screenshots/102.PNG)

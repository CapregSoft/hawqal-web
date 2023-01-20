# Go

### Installation

To install Hawqal, run the following command:

```go
go get github.com/CapregSoft/Hawqal-go
```
### Functions

- `GetCountries()`
- `GetCountry()`
- `GetStates()`
- `GetState()`
- `GetCities()`
- `GetCity()`



## Filters

By default, all filters are 'false' to ensure that only the desired data is displayed.

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

# Usage/Examples

## Get Started
```go
package main

import (
  "fmt"
   hawqal "gihtub.com/CapregSoft/Hawqal-go"
  "log"
)
```
# Countries

- ### Returns Countries 


```go
hawqal.GetCountries()

[
  { 
    "Country_name": "Afghanistan",
    "Currency": "AFN", 
    "Currency_name": "Afghan afghani",
    "Currency_symbol": "؋",
    "Capital": "Kabul",
    "Iso_code": "AFG",
    "Phone_code": "+93",
    "Region": "Asia",
    "Subregion": "Southern Asia",
    "Country_domain": ".af",
    "Timezone": "Asia ",
    "Zone_city":" Kabul  ",
    "UTC": " 04:30  ",
    "Latitude": "33",
    "Longitude": "65"
  },
  {
    "Country_name": "Zimbabwe",
    "Currency": "ZWL",
    "Currency_name": "Zimbabwe Dollar",
    "Currency_symbol": "$",
    "Capital": "Harare",
    "Iso_code": "ZWE",
    "Phone_code": "+263",
    "Region": "Africa",
    "Subregion": "Eastern Africa",
    "Country_domain": ".zw",
    "Timezone": "Africa ",
    "Zone_city": " Harare  ",
    "UTC": " 02:00  ",
    "Latitude": "-20",
    "Longitude": "30"
  },
  ...
]
```




- ### Returns Countries with Filters

```go
hawqal.GetCountries(&models.CountryFilter{Currency: true, Currency_name: true, Currency_symbol: true})

[
  {
    "Currency": "AUD",
    "Currency_name": "Australian dollar",
    "Currency_symbol": "$"
  },
  {
    "Currency": "ZWL",
    "Currency_name": "Zimbabwe Dollar",
    "Currency_symbol": "$"
  },
  ...

]
  ```
  
   

# Country
- ### Returns Single Country along with Filters


```go
hawqal.GetCountry("pakistan", &models.CountryFilter{Currency: true, Country_name: true, Currency_symbol: true})

[
  {
    "Country_name": "Pakistan",
    "Currency": "PKR",
    "Currency_symbol": "₨"
  }
]
  ```

- ### Returns single Country data

```go
hawqal.GetCountry("Pakistan")

[
  {
    "Country_name": "Pakistan",
    "Currency": "PKR",
    "Currency_name": "Pakistani rupee",
    "Currency_symbol": "₨",
    "Capital": "Islamabad",
    "Iso_code": "PAK",
    "Phone_code": "+92",
    "Region": "Asia",
    "Subregion": "Southern Asia",
    "Country_domain": ".pk",
    "Timezone": "Asia ",
    "Zone_city": " Karachi  ",
    "UTC": " 05:00  ",
    "Latitude": "30",
    "Longitude": "70"
  }

]
  ```
# States

- ### Returns States 

```go
hawqal.GetStates()

[
  {
    "Country_name": "Uzbekistan",
    "State_id": 2543,
    "State_name": "Qashqadaryo Region",
    "Latitude": "38.8986231",
    "Longitude": "66.0463534"
  },

  {
    "Country_name": "Zimbabwe",
    "State_id": 1957,
    "State_name": "Midlands Province",
    "Latitude": "-19.0552009",
    "Longitude": "29.6035495"
  },
  ...

]
  ```

- ### Returns States of single country

```go
hawqal.GetStates(&models.StateFilter{CountryName: "pakistan"})

[
  {
    "Country_name": "Pakistan",
    "State_id": 3172,
    "State_name": "Azad Kashmir",
    "Latitude": "33.9259055",
    "Longitude": "73.7810334"
  },
  
  {
    "Country_name": "Pakistan",
    "State_id": 3175,
    "State_name": "Sindh",
    "Latitude": "25.8943018",
    "Longitude": "68.5247149"
  },
  ...
]
  ```

# State

- ### Returns Single State

```go
hawqal.GetState("punjab")

[
  {
    "Country_name": "India",
    "State_id": 4015,
    "State_name": "Punjab",
    "Latitude": "31.1471305",
    "Longitude": "75.3412179"
  },
  {
    "Country_name": "Pakistan",
    "State_id": 3176,
    "State_name": "Punjab",
    "Latitude": "31.1471305",
    "Longitude": "75.3412179"
  }
]
  ```

- ### Returns Single State with Filters

```go
hawqal.GetState("punjab", &models.StateFilter{CountryName: "pakistan"})

[
  {
    "Country_name": "Pakistan",
    "State_id": 3176,
    "State_name": "Punjab",
    "Latitude": "31.1471305",
    "Longitude": "75.3412179"
  }
]

  ```

# Cities

- ### Returns Cities 

```go
hawqal.GetCities()

[
   {
    "Country_name": "France",
    "State_id": 4820,
    "State_name": "Grand-Est",
    "City_id": 42622,
    "City_name": "Kuntzig",
    "Latitude": "49.34731",
    "Longitude": "6.2371"
  },
  ...

]
  ```

- ### Returns Cities of a Country

```go
hawqal.GetCities(&models.CityFilter{CountryName: "pakistan"})

[
  {
    "Country_name": "Pakistan",
    "State_id": 3175,
    "State_name": "Sindh",
    "City_id": 85573,
    "City_name": "Lakhi",
    "Latitude": "27.84884",
    "Longitude": "68.69972"
  },

  {
    "Country_name": "Pakistan",
    "State_id": 3175,
    "State_name": "Sindh",
    "City_id": 85765,
    "City_name": "Warah",
    "Latitude": "27.44805",
    "Longitude": "67.79654"
  },
  ...

]
```

- ### Returns Cities with Filters
 
```go
hawqal.GetCities(&models.CityFilter{StateName: "Punjab", Filter: &models.CityData{CityId: true, CityName: true }})

[
  {
    "City_id": 133082,
    "City_name": "Mansa"
  },
  
  {
    "City_id": 85769,
    "City_name": "Zahir Pir"
  }
  ...
]
```


- ### Returns Cities by Country and State

```go
hawqal.GetCities(&models.CityFilter{CountryName: "pakistan", StateName: "punjab", Filter: &models.CityData{Latitude: true, Longitude: true}})

[
  {
    "Latitude": "32.34464",
    "Longitude": "74.8999"
  },
  
  {
    "Latitude": "28.81284",
    "Longitude": "70.52341"
  },
  ...
]
  ```


# City

- ### Returns Single City 


```go
hawqal.GetCity("wah")

[
  {
    "Country_name": "Pakistan",
    "State_id": 3176,
    "State_name": "Punjab",
    "City_id": 143779,
    "City_name": "Wah",
    "Latitude": "33.81",
    "Longitude": "72.70972222"
  }

]
  ```

- ### Returns Single City with Filter


```go
hawqal.GetCity("Wah", &models.CityFilter{CountryName: "Pakistan", StateName: "Punjab"})

[
  {
    "Country_name": "Pakistan",
    "State_id": 3176,
    "State_name": "Punjab",
    "City_id": 143779,
    "City_name": "Wah",
    "Latitude": "33.81",
    "Longitude": "72.70972222"
  }
]
  ```


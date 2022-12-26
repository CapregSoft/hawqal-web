# Introduction

The <span style="font-weight:bold; color:#000000;">`hawqal`</span> package is a library that provides a list of countries, states, and cities in the world. It is available in Node.js, Go, and Python.


<span style="font-weight:bold; font-size:20px;">Functionality</span>

- Get all countries
- Get states by country
- Get cities by country
- Get cities by state


## Go


### Installation

To install Hawqal, run the following command:

```code
go get github.com/CapregSoft/Hawqal-go
```
### Functions

- `Get All Countries`
- `Get All Cities`
- `Get All States`
- `Get State By Country`
- `Get Cities By Country`
- `Get Cities By State`

### Usage/Examples

#### Get Started
```code
package main

import (
  "fmt"
   hawqal "gihtub.com/CapregSoft/Hawqal-go"
  "log"
)
```
#### Get All Countries


To get a list of all countries, use the `hawqal.GetCountriesData()` function whch returns countries & error.

```code
  countries, err := hawqal.GetCountriesData()
  if err != nil {
    log.Fatalf("Error %v", err)
  }
  fmt.Print("Country")
  for _, country := range countries {
    fmt.Printf("ID :: %v - Country :: %v\n", *country.CountryID, *country.CountryName)
  }
```
 <span style="font-weight:bold;"> Success Response</span>
```
  {
    Countries : ['Afghanistan', 'Aland Islands', 'Albania', 'Algeria', . . . ]
  }

```

#### Get All Cities

To get a list of all countries, use the `hawqal.GetCitiesData()` function whch returns countres & error.

```code
  cities, err := hawqal.GetCitiesData()
	if err != nil {
		log.Fatalf("Error %v", err)
	}

	fmt.Print("Cities")
	for _, city := range cities {
		fmt.Printf("City :: %v - Country :: %v \n", *city.CityName, *city.CountryName)
	}
  ```

 <span style="font-weight:bold;"> Success Response</span>
```
  {
    Cities : ['Haripur','Abbotabad','WahCantt','Topi',........]
  }

```

#### Get All States


To get a list of all states, use the `hawqal.GetStatesData()` function:

```code
    states, err := hawqal.GetStatesData()
    if err != nil {
      log.Fatalf("Error %v", err)
    }

    fmt.Print("States")
    for _, state := range states {
      fmt.Printf("State :: %v - Country :: %v \n", *state.StateName, *state.CountryName)
    }
  ```
 <span style="font-weight:bold;"> Success Response</span>
```
{
  States : ['Alabama', 'Alaska', 'American Samoa', 'Arizona', . . . ]
}
```
#### Get States By Country Name

To get a list of states for a specific country, use the `GetStatesByCountry` function:

```code
  statesByCountry, err := hawqal.GetStatesByCountry(countryName)
	if err != nil {
		log.Fatalf("Error %v", err)
	}
	fmt.Printf("states: %v  ", statesByCountry)
```
<span style="font-weight:bold;"> Success Response</span>
```
{
  States : ['Alabama', 'Alaska', 'American Samoa', 'Arizona', . . . ]
}
```

#### Get Cities By Country

To get a list of cities for a specific state, use the `GetCitiesByCountryData` function:

```code
  citiesByCountry, err := hawqal.GetCitiesByCountryData(citiesCountryName)
  if err != nil {
    log.Fatalf("Error %v", err)
  }
  fmt.Print("Cities For Country ", citiesCountryName)
  for _, city := range citiesByCountry {
    fmt.Printf("City :: %v \n", *city.CityName)
  }
```
<span style="font-weight:bold;"> Success Response</span>
```
  {
    Cities : ['Haripur','Abbotabad','WahCantt','Topi',........]
  }
```

#### Get Cities By State
To get a list of cities for a specific state, use the `GetCitiesByState` function:

```code 
  citiesByState, err := hawqal.GetCitiesByState(stateName)
	if err != nil {
		log.Fatalf("Error %v", err)
	}

	fmt.Print("Cities For State ", stateName)
	for _, city := range citiesByState {
		fmt.Printf("City :: %v \n", *city.CityName)
	}
```
<span style="font-weight:bold;"> Success Response</span>
```
{
  Cities : ['Haripur','Abbotabad','WahCantt','Topi',........]
}
```

## Node Js

### Installation

To install Hawqal, run the following command:

```code
npm i @capregsoft/hawqal
```
### Usage/Examples

#### All Countries


To get a list of all countries, use the `getAllCountries` function:

```code
const worldData = require('@capregsoft/hawqal')
const getCountries = async () => {
  console.log(await worldData.getAllCountries());
}
getCountries();
```
 <span style="font-weight:bold;"> Success Response</span>


```
{
  data: [
    { country_id: 1, country_name: 'Afghanistan' },
    { country_id: 2, country_name: 'Aland Islands' },
    { country_id: 3, country_name: 'Albania' },
    { country_id: 4, country_name: 'Algeria' },
    { country_id: 5, country_name: 'American Samoa' },
    { country_id: 6, country_name: 'Andorra' },
    { country_id: 7, country_name: 'Angola' }
    ...
  ]
}
```
 <span style="font-weight:bold;"> Error Response</span>
```code
{ data: [] }
```

#### States By Country Name

To get a list of states for a specific country, use the `getAllStatesByCountryName` function:

```code
const worldData = require('@capregsoft/hawqal')
const getStates = async () => {
  console.log(await worldData.getAllStatesByCountryName('pakistan'));
}
getStates();
```

Use `async` and `await` to get a meaningful response.

#### Cities By State & Country Name

To get a list of cities for a specific state, use the `getCitiesByStateName` function:

```code
const worldData = require('@capregsoft/hawqal')
const getCities = async () => {
  console.log(await worldData.getCitiesByStateName('punjab'));
}
getCities();

const getCitieByCountry = async () => {
  console.log(await worldData.getCitiesByCountryName('Finland'));
}
getCitieByCountry();
```

## Python

To install the package in Python, run the following command:

### Installation

```code
  pip install hawqal
```
#### Usage/Example

#### Getting a list of Countries
To get a list of all countries, you can use the <span style="font-weight:bold; color:#000000;">`getCountries()`</span> function.

``` code
  from hawqal.country import Country
  Country.getCountries()

```
<span style="font-weight:bold;"> Success Response</span>
```
  ['Afghanistan', 'Aland Islands', 'Albania', 'Algeria', . . . ]
```

#### Getting a list of Cities
To get a list of all Cities, you can use the <span style="font-weight:bold; color:#000000;">`getCities()`</span> function.

``` code
  from hawqal.cities import City
  City.getCities("countries name", "state")
```
<span style="font-weight:bold;"> Success Response</span>
```
  ['Haripur','Abbotabad','Topi',........]
```

#### Getting a list of States
To get a list of all States, you can use the <span style="font-weight:bold; color:#000000;">`getStates()`</span> function.

``` code
  from hawqal.states import StatesByCountry
  StatesByCountry.getStates()
```

<span style="font-weight:bold;"> Success Response</span>
```code
   ['Alabama', 'Alaska', 'American Samoa', 'Arizona', . . . ]
```

#
#### Getting Cities By Country
To get a list of all Countries, you can use the <span style="font-weight:bold; color:#000000;">`CitiesByCountry()`</span> function.

``` code
  from hawqal.citiesbycountry import CitiesByCountry
  CitiesByCountry.getCities("country name")
```
<span style="font-weight:bold;"> Success Response</span>
```code
   ['Haripur','Abbotabad','WahCantt','Topi',........]
```

#
#### Getting Cities By State
To get a list of all Cities By State, you can use the <span style="font-weight:bold; color:#000000;">`CitiesByCountry()`</span> function.

``` code
  from hawqal.cities import City
  City.getCities("", "state")
```
<span style="font-weight:bold;"> Success Response</span>
```code
   ['Haripur','Abbotabad','WahCantt','Topi',........]
```

#### Getting States by Country
To get a list of all states by country, you can use the <span style="font-weight:bold; color:#000000;">`CitiesByCountry()`</span> function.

``` code
  from hawqal.states import StatesByCountry
  StatesByCountry.getStates("country name")
```
<span style="font-weight:bold;"> Success Response</span>
```code
   ['Alabama', 'Alaska', 'American Samoa', 'Arizona', . . . ]
```
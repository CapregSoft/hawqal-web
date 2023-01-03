# js

### Installation

To install Hawqal, run the following command:

```js
js get github.com/CapregSoft/Hawqal-js
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
```js
package main

import (
  "fmt"
   hawqal "gihtub.com/CapregSoft/Hawqal-js"
  "log"
)
```
#### Get All Countries


To get a list of all countries, use the `hawqal.GetCountriesData()` function whch returns countries & error.

```js
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

To get a list of all cities, use the `hawqal.GetCitiesData()` function whch returns cities & error.

```js
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

```js
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

```js
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

To get a list of cities for a specific country, use the `GetCitiesByCountryData` function:

```js
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

```js 
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


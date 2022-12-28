<p><a href="https://github.com/CapregSoft/hawqal-web/blob/master/docs/README.md" target="_blank" rel="noopener"><img src="https://github.githubassets.com/images/icons/emoji/unicode/1f4dd.png?v8.png" alt="memo" class="emoji" loading="lazy"> Edit Document</a></p>

# Introduction

The <span style="font-weight:bold; color:#000000;">`hawqal`</span> package is a library that provides a list of countries, states, and cities in the world. It is available in Node.js, Go, and Python.


<span style="font-weight:bold; font-size:20px;">Functionality</span>

- Get all countries
- Get states by country
- Get cities by country
- Get cities by state


<p><a href="https://github.com/CapregSoft/hawqal-web/blob/master/docs/go.md" target="_blank" rel="noopener"><img src="https://github.githubassets.com/images/icons/emoji/unicode/1f4dd.png?v8.png" alt="memo" class="emoji" loading="lazy"> Edit Document</a></p>


<span style="font-size:40px;">Go</span>


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

To get a list of all cities, use the `hawqal.GetCitiesData()` function whch returns cities & error.

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

To get a list of cities for a specific country, use the `GetCitiesByCountryData` function:

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



<span style="font-size:40px;">Node Js</span>

### Installation

To install Hawqal, run the following command:

```code
npm i @capregsoft/hawqal
```

### Functions

- `Get Countries`
- `Get Cities`
- `Get States`


### Usage/Examples
Use `Asyc` and `await` to get meaningful response
#### All Countries


To get a list of all countries, use the `getCountries` function:

```code
const worldData = require('@capregsoft/hawqal')
const getData = async () =>{
    console.log(await worldData.getCountries());
}
getData();
```
 <span style="font-weight:bold;"> Success Response</span>
```
 [
  'Afghanistan',
  'Aland Islands',
  'Albania',
  'Algeria',
  'American Samoa',
  'Andorra',
  'Angola',
  'Anguilla',...
]
```


#### All States

To get a list of all countries, use the `getStates` function:

```code
const worldData = require('@capregsoft/hawqal')
const getStates = async () =>{
    console.log(await await index.getStates('pakistan'));
}
getStates();
```
 <span style="font-weight:bold;"> Success Response</span>
```
[
  'Azad Kashmir',
  'Balochistan',
  'Federally Administered Tribal Areas',
  'Gilgit-Baltistan',
  'Islamabad Capital Territory',
  'Khyber Pakhtunkhwa',
  'Punjab',
  'Sindh'
]
```
#### Cities By State & Country Name

To get a list of cities for a specific state, cities or country, use the `getCities` parameterized function:

```code
const worldData = require('@capregsoft/hawqal')
const getCities = async () =>{
     //get all cities
    console.log(await await index.getCities());

    //get state cities
    console.log(await await index.getCities('','punjab'));
    
    //get country cities
    console.log(await await index.getCities('pakistan'));
    
    //get country,state cities
    console.log(await await index.getCities('pakistan','punjab'));
}
getCities();
```
 <span style="font-weight:bold;"> Success Response</span>
```
[
  'Fatehgarh Sahib', 'Firozpur',     'Firozpur District',
  'Fazilka',         'Gardhiwala',   'Garhshankar',
  'Ghanaur',         'Giddarbaha',   'Gurdaspur',
  'Guru Har Sahai',  'Hariana',      'Hoshiarpur',
  'Hajipur',         'Jagraon',      'Jaito',
]
```

 <span style="font-weight:bold;"> Error Response</span>
```code
[]
Db connection Error!!!
```

<span style="font-size:40px;">Python</span>

To install the package in Python, run the following command:

### Installation

```code
  pip install hawqal
```

### Functions

- `Getting a list of Countries`
- `Getting a list of Cities`
- `Getting a list of States`
- `Getting Cities By Country`
- `Getting Cities By State`
- `Getting States by Country`

### Usage/Example

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
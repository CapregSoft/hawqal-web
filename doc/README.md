# Introduction

The <span style="font-weight:bold; color:#000000;">`hawqal`</span> package is a library that provides a list of countries, states, and cities in the world. It is available in Node.js, Go, and Python.


<span style="font-weight:bold; font-size:20px;">Functionality</span>

- Get all countries
- Get states by country
- Get cities by country
- Get cities by state


## Node JS

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
```

## Go


### Installation

To install Hawqal, run the following command:

```code
https://github.com/CapregSoft/Hawqal-go
```
### Functions

- `Get Countries`
- `Get States`
- `Get Cities`
- `Get Cities By State`
- `Get State By Country`
- `Get Cities By Country`

### Usage/Examples

#### Getting Started
```code
package main

import (
     "fmt"
      hawqal "gihtub.com/CapregSoft/Hawqal-go"
     "log"
)
```
#### All Countries


To get a list of all countries, use the `hawqal.GetCountriesData()` function:

```code
func main(){
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
{}
```
 <span style="font-weight:bold;"> Error Response</span>
```code
{}
```
hawqal.GetStatesData()

#### All States


To get a list of all states, use the `hawqal.GetStatesData()` function:

```code
    countries, err := hawqal.GetCountriesData()
	if err != nil {
		log.Fatalf("Error %v", err)
	}
	fmt.Print("Country")

	for _, country := range countries {
		//the variable country holds the one country name &  its specific Id
		fmt.Printf("ID :: %v - Country :: %v\n", *country.CountryID, *country.CountryName)
	}
```
 <span style="font-weight:bold;"> Success Response</span>
```
{

}
```
 <span style="font-weight:bold;"> Error Response</span>
```code
{ }
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
```

## Python

To install the package in Python, run the following command:

```code
pip install world-countries-states-cities
```
# Usage
## Getting a list of countries
To get a list of all countries, you can use the <span style="font-weight:bold; color:#000000;">`getCountries()`</span> function. This function returns an array of objects, each representing a country. The objects have the following properties:

<ul>
<li>`<span style="font-weight:bold">name</span>`: The name of the country.</li>
<li>`<span style="font-weight:bold">code</span>`: The two-letter code for the country.</li>
</ul>

Here is an example of how to use the <span style="font-weight:bold; color:#000000;">`getCountries()`</span> function in <span style="font-weight:bold; color:#000000;">`NodeJs`</span>:

``` code
const { getCountries } = require('world-countries-states-cities');

const countries = getCountries();
console.log(countries);
```

Here is an example of how to use the <span style="font-weight:bold; color:#000000;">`getCountries()`</span> function in <span style="font-weight:bold; color:#000000;">`Go`</span>:

``` code
package main
import (
	"fmt"
	"github.com/world-countries-states-cities/world-countries-states-cities"
)

func main() {
	countries := worldcountriesstatescities.GetCountries()
	fmt.Println(countries)
}
```

Here is an example of how to use the <span style="font-weight:bold; color:#000000;">`get_countries()`</span> function in <span style="font-weight:bold; color:#000000;">`Python`</span>:

```code
from world_countries_states_cities import get_countries

countries = get_countries()
print(countries)
```
## Getting a list of states for a specific country
    To get a list of states for a specific country, you can use the <span style="font-weight:bold; color:#000000;">`getStates(countryCode)`</span> function. This function takes a two-letter country code as an argument and returns an array of objects, each representing a state. The objects have the following properties:

    <ul>
    <li>`<span style="font-weight:bold">name</span>`: The name of the country.</li>
    <li>`<span style="font-weight:bold">code</span>`: The two-letter code for the country.</li>
    </ul>

    Here is an example of how to use the <span style="font-weight:bold; color:#000000;">`getStates()`</span> function in <span style="font-weight:bold; color:#000000;">`NodeJs`</span>:

``` code
const { getStates } = require('world-countries-states-cities');

const states = getStates('US');
console.log(states);
```

Here is an example of how to use the <span style="font-weight:bold; color:#000000;">`getStates()`</span> function in <span style="font-weight:bold; color:#000000;">`Go`</span>:

``` code
package main

import (
	"fmt"
	"github.com/world-countries-states-cities/world-countries-states-cities"
)
func main() {
	states
```

Here is an example of how to use the <span style="font-weight:bold; color:#000000;">`get_countries()`</span> function in <span style="font-weight:bold; color:#000000;">`Python`</span>:

```code
from world_countries_states_cities import get_countries

countries = get_countries()
print(countries)
```

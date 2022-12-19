
# Introduction

The <span style="font-weight:bold; color:#000000;">`world-countries-states-cities`</span> package is a library that provides a list of countries, states, and cities in the world. It is available in Node.js, Go, and Python.

# Installation
## Node JS
To install the package in Node.js, run the following command:

```code
npm install world-countries-states-cities
```
## Go

To install the package in Go, run the following command:

```code
go get github.com/world-countries-states-cities/world-countries-states-cities
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

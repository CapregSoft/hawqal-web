
# js

To install the package in js, run the following command:

### Installation

```js
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

```js
  from hawqal.country import Country
  Country.getCountries()

```
<span style="font-weight:bold;"> Success Response</span>
```
  ['Afghanistan', 'Aland Islands', 'Albania', 'Algeria', . . . ]
```

#### Getting a list of Cities
To get a list of all Cities, you can use the <span style="font-weight:bold; color:#000000;">`getCities()`</span> function.

```js
  from hawqal.cities import City
  City.getCities("countries name", "state")
```
<span style="font-weight:bold;"> Success Response</span>
```
  ['Haripur','Abbotabad','Topi',........]
```

#### Getting a list of States
To get a list of all States, you can use the <span style="font-weight:bold; color:#000000;">`getStates()`</span> function.

```js
  from hawqal.states import StatesByCountry
  StatesByCountry.getStates()
```

<span style="font-weight:bold;"> Success Response</span>
```
   ['Alabama', 'Alaska', 'American Samoa', 'Arizona', . . . ]
```

#### Getting Cities By Country
To get a list of all Cities By Country, you can use the <span style="font-weight:bold; color:#000000;">`CitiesByCountry()`</span> function.

``` js
  from hawqal.citiesbycountry import CitiesByCountry
  CitiesByCountry.getCities("country name")
```
<span style="font-weight:bold;"> Success Response</span>
```
   ['Haripur','Abbotabad','WahCantt','Topi',........]
```

#### Getting Cities By State
To get a list of all Cities By State, you can use the <span style="font-weight:bold; color:#000000;">`CitiesByCountry()`</span> function.

```js
  from hawqal.cities import City
  City.getCities("", "state")
```
<span style="font-weight:bold;"> Success Response</span>
```
   ['Haripur','Abbotabad','WahCantt','Topi',........]
```

#### Getting States by Country
To get a list of all States By Country, you can use the <span style="font-weight:bold; color:#000000;">`CitiesByCountry()`</span> function.

```js
  from hawqal.states import StatesByCountry
  StatesByCountry.getStates("country name")
```
<span style="font-weight:bold;"> Success Response</span>
```
   ['Alabama', 'Alaska', 'American Samoa', 'Arizona', . . . ]
```
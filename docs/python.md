<p><a href="https://github.com/CapregSoft/hawqal-web/blob/master/docs/README.md" target="_blank" rel="noopener"><img src="https://github.githubassets.com/images/icons/emoji/unicode/1f4dd.png?v8.png" alt="memo" class="emoji" loading="lazy"> Edit Document</a></p>

<span style="font-size:40px;">Python</span>

To install the package in Python, run the following command:

### Installation

```code
  pip install hawqal
```
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
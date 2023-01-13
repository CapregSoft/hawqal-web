# Node Js

### Installation

To install Hawqal, run the following command:

```js
npm i @capregsoft/hawqal
```

### Functions

- `Get Countries`
- `Get Country`
- `Get States`
- `Get State`
- `Get Cities`
- `Get City`

### Filters
By default all Filters are set to `true`. If certain value is not required set that filter to `false`
- Filters

|   Country Filter      |State Filter   |City Filter
|----------             |----------     |----------
|country_name           |country_name   |city_id
|iso_code               |state_id       |city_name
|phone_code             |state_name     |state_name
|capital                |longitude      |state_id
|currency               |latitude       |country_name
|currency_name                          |longitude
|currency_symbol                        |latitude
|region
|subregion
|country_domain
|time_zone
|zone_city
|UTC
|longitude
|latitude

### Usage/Examples

Use `Asyc` and `await` to get meaningful response

#### Countries
  - Country

To get a country details witout filter, use the `getCountry` function: with country Name

```js
const hawqal = require("@capregsoft/hawqal");
const getData = async (country) => console.log(await hawqal.getCountry(country));
getData('pakistan');
```
<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    country_name: 'Pakistan',
    iso_code: 'PAK',
    phone_code: '+92',
    capital: 'Islamabad',
    currency: 'PKR',
    currency_name: 'Pakistani rupee',
    currency_symbol: '₨',
    country_domain: '.pk',
    region: 'Asia',
    subregion: 'Southern Asia',
    timezone: 'Asia ',
    UTC: ' 05:00  ',
    latitude: '30',
    longitude: '70'
  }
]

```

To get a country with  Filters put 2nd parameter as an `object` in `getCountry`

```js
const getCountryField = async (countryName,filters) =>
  console.log(
    await hawqal.getCountry(countryName,filters)
  );
getCountryField('pakistan',{
      phone_code: true,
      iso_code: true,
      country_name:true
    });
```
<span style="font-weight:bold;"> Success Response</span>

```
[ { phone_code: '+92', iso_code: 'PAK', country_name: 'Pakistan' } ]
```

To get a list of countries with filters use `getCountries`

```js
const getCountries = async (filters) =>
  console.log(
    await hawqal.getCountries(filters));
getCountries({
      phone_code: true,
      iso_code: true,
      country_name:true
     });
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  { 
    phone_code: '+93', 
    iso_code: 'AFG', 
    country_name: 'Afghanistan' 
  },
  {
    phone_code: '+340',
    iso_code: 'ALA',
    country_name: 'Aland Islands'
  },
  ...
]
  ```

#### States

To get state without filters, use the `getState` function:

```js
const getState = async (state) => console.log(await hawqal.getState(state));
getState('punjab');
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    state_id: 4015,
    state_name: 'Punjab',
    country_name: 'India',
    latitude: '31.1471305',
    longitude: '75.3412179'
  },
  {
    state_id: 3176,
    state_name: 'Punjab',
    country_name: 'Pakistan',
    latitude: '31.1471305',
    longitude: '75.3412179'
  }
]
```

To get state with filters put `object` as a filter, use the `getState` function:

```js
const getState = async (state) => console.log(await hawqal.getState(state,{
  longitude:true,
  state_name:true,
  country_name:true
}));
getState('punjab');
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  { 
    longitude: '75.3412179', 
    state_name: 'Punjab', 
    country_name: 'India' 
  },
  { 
    longitude: '75.3412179', 
    state_name: 'Punjab', 
    country_name: 'Pakistan'
  }
]
```
To get a list of all states of specific country with filters use `getStates` function:

```js
const allStatesCountry = async (country) =>
  console.log(await hawqal.getStates(country,{
    longitude:true,
    state_name:true,
    country_name:true
}));
allStatesCountry("finland");
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    longitude: '19.9156105',
    state_name: 'Åland Islands',
    country_name: 'Finland'
  },
  {
    longitude: '25.5549445',
    state_name: 'Central Finland',
    country_name: 'Finland'
  },
  {
    longitude: '24.0013631',
    state_name: 'Central Ostrobothnia',
    country_name: 'Finland'
  },
  ...
]
```
#### Cities 

To get a city detail with filters use `getCity` function:

```js
const getCity = async () => console.log(await hawqal.getCity('islamabad',{
    city_name:true,
    state_name:true,
    country_name:true
}));
getCity();
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    city_name: 'Islamabad',
    state_name: 'Islamabad Capital Territory',
    country_name: 'Pakistan'
  }
]
```

To get all cities of specific country with filters use `getCities` function:

```js
const getCities = async (country,state,filter) => console.log(await hawqal.getCities(country,state,filter));
getCities('finland','',{
    city_name:true,
    state_name:true,
    country_name:true
});
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    city_name: 'Äänekoski',
    state_name: 'Central Finland',
    country_name: 'Finland'
  },
  {
    city_name: 'Hankasalmi',
    state_name: 'Central Finland',
    country_name: 'Finland'
  },
  {
    city_name: 'Jämsä',
    state_name: 'Central Finland',
    country_name: 'Finland'
  },
  ...
]
```


To get all cities of specific state of any country with filters use `getCities` function:

```js
const getCities = async (country,state,filter) => console.log(await hawqal.getCities(country,state,filter));
getCities('','Kainuu',{
    city_name:true,
    state_name:true,
    country_name:true
});
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    city_name: 'Hyrynsalmi',
    state_name: 'Kainuu',
    country_name: 'Finland'
  },
  {
    city_name: 'Kajaani',
    state_name: 'Kainuu',
    country_name: 'Finland'
  },
  { 
    city_name: 'Kuhmo', 
    state_name: 'Kainuu', 
    country_name: 'Finland' 
  },
  ...
]

```

To get all cities of specific state and specific country with filters use `getCities` function:

```js
const getCities = async (country,state,filter) => console.log(await hawqal.getCities(country,state,filter));
getCities('pakistan','punjab',{
    city_name:true,
    state_name:true,
    country_name:true
});
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    city_name: 'Ahmadpur Sial',
    state_name: 'Punjab',
    country_name: 'Pakistan'
  },
  {
    city_name: 'Ahmedpur East',
    state_name: 'Punjab',
    country_name: 'Pakistan'
  },
  {
    city_name: 'Alipur Chatha',
    state_name: 'Punjab',
    country_name: 'Pakistan'
  },
  ...
]

```


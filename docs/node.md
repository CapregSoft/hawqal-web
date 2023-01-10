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
const worldData = require("@capregsoft/hawqal");
const getData = async (country) => console.log(await worldData.getCountry(country));
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
const getCountryField = async () =>
  console.log(
    await hawqal.getCountry('pakistan',{
      phone_code: false,
      iso_code: false,
      country_name:false
    })
  );
getCountryField();
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
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

To get a list of countries with filters use `getCountries`

```js
const getCountries = async () =>
  console.log(
    await hawqal.getCountries({
     {
      phone_code: false,
      iso_code: false,
      country_name:false
    }
    )
  );
getCountries();
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    capital: 'Kabul',
    currency: 'AFN',
    currency_name: 'Afghan afghani',
    currency_symbol: '؋',
    country_domain: '.af',
    region: 'Asia',
    subregion: 'Southern Asia',
    timezone: 'Asia ',
    UTC: ' 04:30  ',
    latitude: '33',
    longitude: '65'
  },
  {
    capital: 'Mariehamn',
    currency: 'EUR',
    currency_name: 'Euro',
    currency_symbol: '€',
    country_domain: '.ax',
    region: 'Europe',
    subregion: 'Northern Europe',
    timezone: 'Europe ',
    UTC: ' 02:00  ',
    latitude: '60.116667',
    longitude: '19.9'
  },
  ....
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
  longitude:false,
  state_name:false,
  state_id:false
}));
getState('punjab');
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  { country_name: 'India', 
    latitude: '31.1471305' 
  },
  { country_name: 'Pakistan', 
    latitude: '31.1471305' 
  }
]
```

To get a list of all states of specific country with filters use `getStates` function:

```js
const allStatesCountry = async (country) =>
  console.log(await hawqal.getStates(country,{
    longitude:false,
    state_name:false,
    state_id:false
}));
allStatesCountry("finland");
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  { country_name: 'Finland', latitude: '60.1785247' },
  { country_name: 'Finland', latitude: '62.5666743' },
  { country_name: 'Finland', latitude: '63.5621735' },
  { country_name: 'Finland', latitude: '60.3627914' },
  { country_name: 'Finland', latitude: '64.3736564' },
  { country_name: 'Finland', latitude: '60.780512' },
  { country_name: 'Finland', latitude: '67.9222304' },
  { country_name: 'Finland', latitude: '62.8062078' },
  { country_name: 'Finland', latitude: '65.279493' },
  { country_name: 'Finland', latitude: '63.08448' },
  { country_name: 'Finland', latitude: '63.1181757' },
  { country_name: 'Finland', latitude: '61.3230041' },
  { country_name: 'Finland', latitude: '61.6986918' },
  { country_name: 'Finland', latitude: '61.5932758' },
  { country_name: 'Finland', latitude: '61.1181949' },
  { country_name: 'Finland', latitude: '62.9433099' },
  { country_name: 'Finland', latitude: '61.6945148' },
  { country_name: 'Finland', latitude: '60.907015' },
  { country_name: 'Finland', latitude: '60.21872' }
]
```

#### Cities 

To get a city detail with filters use `getCity` function:

```js
const getCity = async () => console.log(await hawqal.getCity('islamabad',{
  state_id:false,
  state_name:false
}));
getCity();
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    city_id: 85475,
    city_name: 'Islamabad',
    country_name: 'Pakistan',
    latitude: '33.72148',
    longitude: '73.04329'
  }
]
```

To get all cities of specific country with filters use `getCities` function:

```js
const getCities = async (country,state,filter) => console.log(await hawqal.getCities(country,state,filter));
getCities('findland','',{
  state_id:false,
  state_name:false
});
//first: country
//second: state
//third:  filter
```

<span style="font-weight:bold;"> Success Response</span>

```
[
   {
    city_id: 38949,
    city_name: 'Nagu',
    country_name: 'Finland',
    latitude: '60.19375',
    longitude: '21.90972'
  },
  {
    city_id: 38955,
    city_name: 'Nousiainen',
    country_name: 'Finland',
    latitude: '60.60416',
    longitude: '22.07926'
  },
  {
    city_id: 38963,
    city_name: 'Oripää',
    country_name: 'Finland',
    latitude: '60.85',
    longitude: '22.68333'
  },
  ....
]
```
To get all cities of specific state of any country with filters use `getCities` function:

```js
const getCities = async (country,state,filter) => console.log(await hawqal.getCities(country,state,filter));
getCities('','Kainuu',{
  state_id:false,
  city_id:false
});
//first: country
//second: state
//third:  filter
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
    city_name: 'Hyrynsalmi',
    state_name: 'Kainuu',
    country_name: 'Finland',
    latitude: '64.66667',
    longitude: '28.53333'
  },
  {
    city_name: 'Kajaani',
    state_name: 'Kainuu',
    country_name: 'Finland',
    latitude: '64.22728',
    longitude: '27.72846'
  },
  {
    city_name: 'Kuhmo',
    state_name: 'Kainuu',
    country_name: 'Finland',
    latitude: '64.13333',
    longitude: '29.51667'
  },
  ...
]
```
To get all cities of specific state and specific country with filters use `getCities` function:

```js
const getCities = async (country,state,filter) => console.log(await hawqal.getCities(country,state,filter));
getCities('pakistan','punjab',{
  state_id:false,
  city_id:false
});
//first: country
//second: state
//third:  filter
```

<span style="font-weight:bold;"> Success Response</span>

```
[
  {
      city_name: 'Jand',
      state_name: 'Punjab',
      country_name: 'Pakistan',
      latitude: '33.43304',
      longitude: '72.01877'
    },
    {
      city_name: 'Jandiala Sher Khan',
      state_name: 'Punjab',
      country_name: 'Pakistan',
      latitude: '31.82098',
      longitude: '73.91815'
    },
    {
      city_name: 'Jaranwala',
      state_name: 'Punjab',
      country_name: 'Pakistan',
      latitude: '31.3332',
      longitude: '73.41868'
    },
    {
      city_name: 'Jatoi Shimali',
      state_name: 'Punjab',
      country_name: 'Pakistan',
      latitude: '29.51827',
      longitude: '70.84474'
    },
    ...
]
```

<span style="font-weight:bold;"> Error Response</span>

```js
[];
```

Db connection Error!!!

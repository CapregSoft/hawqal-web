# Node Js

### Installation

To install Hawqal, run the following command:

```js
npm i @capregsoft/hawqal
```

### Functions

- `Get Countries`
- `Get Cities`
- `Get States`


### Usage/Examples
Use `Asyc` and `await` to get meaningful response
#### Countries


To get a list of all countries, use the `getCountries` function:

```js
const worldData = require('@capregsoft/hawqal')
const getData = async () => console.log(await worldData.getCountries());
getData();
```
 <span style="font-weight:bold;"> Success Response</span>
```
 [
  { country_name: 'Afghanistan' },
  { country_name: 'Aland Islands' },
  { country_name: 'Albania' },
  { country_name: 'Algeria' },
  { country_name: 'American Samoa' },
  ....
 ]
```
To get a list of countries with specific fields put `object` parameter in `getCountries`
```country filter fields
const getCountriesField = async ()=> console.log(await worldData.getCountries({coordinates:true,region:true,currency:true,capital:true,timezone:true}))
getCountriesField()
```
<span style="font-weight:bold;"> Success Response</span>
```
 [
   {
    country_name: 'Hungary',
    latitude: '47',
    longitude: '20',
    region: 'Europe',
    subregion: 'Eastern Europe',
    country_domain: '.hu',
    currency: 'HUF',
    currency_symbol: 'Ft',
    currency_name: 'Hungarian forint',
    capital: 'Budapest',
    phone_code: '+36',
    iso_code: 'HUN',
    timezone: 'Europe ',
    zone_city: ' Budapest  ',
    UTC: ' 01:00  '
  },
  ....
 ]
```
To get specific country and specific fields put parameters `country` and `object` in `get countries` 
```specific country & filter fields
const getCountry = async (countryName)=> console.log(await worldData.getCountries(countryName,{coordinates:true,currency:true,capital:true,timezone:false}))
getCountry('findland')
```
<span style="font-weight:bold;"> Success Response</span>
```
 [
  {
    country_name: 'Finland',
    latitude: '64',
    longitude: '26',
    currency: 'EUR',
    currency_symbol: '€',
    currency_name: 'Euro',
    capital: 'Helsinki',
    phone_code: '+358',
    iso_code: 'FIN'
  }
]
```

#### States

To get a list of all states, use the `getStates` function:

```js
const allStates = async () => console.log(await worldData.getStates());
allStates();
```
 <span style="font-weight:bold;"> Success Response</span>
```
[
  { state_name: 'Badakhshan', country_name: 'Afghanistan' },
  { state_name: 'Badghis', country_name: 'Afghanistan' },
  { state_name: 'Baghlan', country_name: 'Afghanistan' },
  { state_name: 'Balkh', country_name: 'Afghanistan' },
  ....
]
```

To get a list of all states of specific country and  use the `getStates` function and put some parameter:

```get states by country name
const allStatesCountry = async (country) => console.log(await worldData.getStates(country,{coordinates:true}));
allStatesCountry('finland');
```
 <span style="font-weight:bold;"> Success Response</span>
```
[
  {
    state_name: 'Åland Islands',
    latitude: '60.1785247',
    longitude: '19.9156105'
  },
  {
    state_name: 'Central Finland',
    latitude: '62.5666743',
    longitude: '25.5549445'
  },
  {
    state_name: 'Central Ostrobothnia',
    latitude: '63.5621735',
    longitude: '24.0013631'
  },
  {
    state_name: 'Finland Proper',
    latitude: '60.3627914',
    longitude: '22.4439369'
  },
  ...
]
```


#### Cities By State & Country Name

To get a list of cities for a specific state,cities or country, use the `getCities` parameterized function:

```js
const getCities = async () =>{
     //get all cities
    console.log(await worldData.getCities());
    //get country cities
    console.log(await  worldData.getCities('finland'));
    //get country,state cities
    console.log(await  worldData.getCities('finland','Finland Proper'));
    //get country,state cities and get fields
    console.log(await worldData.getCities('finland','Finland Proper',{coordinates:true}));
}
getCities();
```
 <span style="font-weight:bold;"> Success Response</span>
```
[
  {
    state_name: 'Åland Islands',
    latitude: '60.1785247',
    longitude: '19.9156105'
  },
  {
    state_name: 'Central Finland',
    latitude: '62.5666743',
    longitude: '25.5549445'
  },
  {
    state_name: 'Central Ostrobothnia',
    latitude: '63.5621735',
    longitude: '24.0013631'
  },
  {
    state_name: 'Finland Proper',
    latitude: '60.3627914',
    longitude: '22.4439369'
  },
  {
    state_name: 'Kainuu',
    latitude: '64.3736564',
    longitude: '28.7437475'
  },
  ...
]
```

 <span style="font-weight:bold;"> Error Response</span>
```js
[]
```
Db connection Error!!!

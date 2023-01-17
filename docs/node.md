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
By default all Filters set to be `false`. If certain value is required set that filter to `true`
- Filters

  |   Country Filter      | State Filter  | City Filter
  |----------             |----------     |----------
  |country_name           |country_name   |city_id
  |iso_code               |state_id       |city_name
  |phone_code             |state_name     |state_name
  |capital                |longitude      |state_id
  |currency               |latitude       |country_name
  |currency_name          |               |longitude
  |currency_symbol        |               |latitude
  |region
  |subregion
  |country_domain
  |time_zone
  |zone_city
  |UTC
  |longitude
  |latitude          

### Usage/Examples


#### Countries
  
- Retrieve  Countries 

  ```js
  const hawqal = require("@capregsoft/hawqal");
  const AllCountries = async () => console.log(await hawqal.getCountries());
  AllCountries();
  ```
  <span style="font-weight:bold;"> Success Response</span>

  ```
  [
    {
      country_name: 'Cameroon',
      iso_code: 'CMR',
      phone_code: '+237',
      capital: 'Yaounde',
      currency: 'XAF',
      currency_name: 'Central African CFA franc',
      currency_symbol: 'FCFA',
      country_domain: '.cm',
      region: 'Africa',
      subregion: 'Middle Africa',
      timezone: 'Africa ',
      UTC: ' 01:00  ',
      latitude: '6',
      longitude: '12'
    },
    {
      country_name: 'Canada',
      iso_code: 'CAN',
      phone_code: '+1',
      capital: 'Ottawa',
      currency: 'CAD',
      currency_name: 'Canadian dollar',
      currency_symbol: '$',
      country_domain: '.ca',
      region: 'Americas',
      subregion: 'Northern America',
      timezone: 'America ',
      UTC: ' -5:00  ',
      latitude: '60',
      longitude: '-95'
    },
    {
      country_name: 'Cape Verde',
      iso_code: 'CPV',
      phone_code: '+238',
      capital: 'Praia',
      currency: 'CVE',
      currency_name: 'Cape Verdean escudo',
      currency_symbol: '$',
      country_domain: '.cv',
      region: 'Africa',
      subregion: 'Western Africa',
      timezone: 'Atlantic ',
      UTC: ' -1:00  ',
      latitude: '16',
      longitude: '-24'
    },
    ...
  ]

  ```

- Search Country 

  ```js
  const searchCountry = async (countryName) => console.log(await hawqal.getCountry(countryName));
  searchCountry('pakistan');
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

- Show all Countries along `filter`

  ```js
  const allCountries = async (filters) =>
    console.log( await hawqal.getCountries(filters));
    allCountries({
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
    { 
      phone_code: '+355', 
      iso_code: 'ALB', 
      country_name: 'Albania' 
    },
    ...
  ]
    ```

#### States

- Retrieve States of all Countries

  ```js
  const allStates = async () => console.log(await hawqal.getStates());
  allStates();
  ```

  <span style="font-weight:bold;"> Success Response</span>

  ```
  [
    {
      state_id: 3901,
      state_name: 'Badakhshan',
      country_name: 'Afghanistan',
      latitude: '36.7347725',
      longitude: '70.8119953'
    },
    {
      state_id: 3871,
      state_name: 'Badghis',
      country_name: 'Afghanistan',
      latitude: '35.1671339',
      longitude: '63.7695384'
    },
    {
      state_id: 3875,
      state_name: 'Baghlan',
      country_name: 'Afghanistan',
      latitude: '36.1789026',
      longitude: '68.7453064'
    },
    ...
  ]
  ```

- Search specific State 
  ```js
  const searchState = async (state) => console.log(await hawqal.getState(state));
  searchState('punjab');

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
- Use of filter 

  ```js
  const allStatesCountry = async (country,filter) => console.log(await hawqal.getStates(country,filter));
  allStatesCountry("finland",{
      state_name:true,
      country_name:true,
      longitude:true,
      latitude:true
  });
  ```

  <span style="font-weight:bold;"> Success Response</span>

  ```
  [
    {
      state_name: 'Åland Islands',
      country_name: 'Finland',
      longitude: '19.9156105',
      latitude: '60.1785247'
    },
    {
      state_name: 'Central Finland',
      country_name: 'Finland',
      longitude: '25.5549445',
      latitude: '62.5666743'
    },
    {
      state_name: 'Central Ostrobothnia',
      country_name: 'Finland',
      longitude: '24.0013631',
      latitude: '63.5621735'
    },
    ...
  ]
  ```
#### Cities 

- Retrieve Cities of Country

  ```js
  const getCities = async (country,state,filter) => console.log(await hawqal.getCities(country,state,filter));
  getCities('finland','',{});
  ```

  <span style="font-weight:bold;"> Success Response</span>

  ```
  [
    {
      city_id: 39132,
      city_name: 'Äänekoski',
      state_id: 1511,
      state_name: 'Central Finland',
      country_name: 'Finland',
      latitude: '62.6',
      longitude: '25.73333'
    },
    {
      city_id: 38760,
      city_name: 'Hankasalmi',
      state_id: 1511,
      state_name: 'Central Finland',
      country_name: 'Finland',
      latitude: '62.38333',
      longitude: '26.43333'
    },
    {
      city_id: 38809,
      city_name: 'Jämsä',
      state_id: 1511,
      state_name: 'Central Finland',
      country_name: 'Finland',
      latitude: '61.8642',
      longitude: '25.19002'
    },
    ...
  ]
  ```
- Retrieve all Cities within State 

  ```js
  const getCities = async (country,state,filter) => console.log(await hawqal.getCities(country,state,filter));
  getCities('','Kainuu',{});
  ```

  <span style="font-weight:bold;"> Success Response</span>

  ```
  [
    {
      city_id: 38778,
      city_name: 'Hyrynsalmi',
      state_id: 1496,
      state_name: 'Kainuu',
      country_name: 'Finland',
      latitude: '64.66667',
      longitude: '28.53333'
    },
    {
      city_id: 38816,
      city_name: 'Kajaani',
      state_id: 1496,
      state_name: 'Kainuu',
      country_name: 'Finland',
      latitude: '64.22728',
      longitude: '27.72846'
    },
    {
      city_id: 38877,
      city_name: 'Kuhmo',
      state_id: 1496,
      state_name: 'Kainuu',
      country_name: 'Finland',
      latitude: '64.13333',
      longitude: '29.51667'
    },
    ...
  ]

  ```


- Search City 

  ```js
  const searchCity = async (city) => console.log(await hawqal.getCity(city));
  searchCity('islamabad');
  ```

  <span style="font-weight:bold;"> Success Response</span>

  ```
  [
    {
      city_id: 85475,
      city_name: 'Islamabad',
      state_name: 'Islamabad Capital Territory',
      state_id: 3169,
      country_name: 'Pakistan',
      latitude: '33.72148',
      longitude: '73.04329'
    }
  ]
  ```



- Search City `with filter`

  ```js
  const searchCity = async (city,filter) => console.log(await hawqal.getCity(city,filter));
  searchCity('islamabad',{
      city_name:true,
      state_name:true,
      country_name:true
  });
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


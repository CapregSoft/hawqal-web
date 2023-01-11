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

![countryPackistanWOFILTER](https://user-images.githubusercontent.com/28805723/211792524-1a3be8d0-2295-4951-a810-59f1f8ea643b.png)

To get a country with  Filters put 2nd parameter as an `object` in `getCountry`

```js
const getCountryField = async (countryName,filters) =>
  console.log(
    await hawqal.getCountry(countryName,filters)
  );
getCountryField('pakistan',{
      phone_code: false,
      iso_code: false,
      country_name:false
    });
```
<span style="font-weight:bold;"> Success Response</span>

![countryPackistanWFILTER](https://user-images.githubusercontent.com/28805723/211792606-988ab5bc-79f7-4696-8862-77b0f008bf03.png)

To get a list of countries with filters use `getCountries`

```js
const getCountries = async (filters) =>
  console.log(
    await hawqal.getCountries(filters));
getCountries({
      phone_code: false,
      iso_code: false,
      country_name:false
     });
```

<span style="font-weight:bold;"> Success Response</span>

![countriesWFILTER](https://user-images.githubusercontent.com/28805723/211792647-6597a654-f1dc-4e5b-af70-ef2124f7a788.png)

#### States

To get state without filters, use the `getState` function:

```js
const getState = async (state) => console.log(await hawqal.getState(state));
getState('punjab');
```

<span style="font-weight:bold;"> Success Response</span>

![stateWOFILTER](https://user-images.githubusercontent.com/28805723/211792838-9826ecee-af74-4c8e-9ee6-eafba844192e.png)

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

![stateWFILTER](https://user-images.githubusercontent.com/28805723/211792873-3ba243bc-e579-4832-a006-4b9e946681fc.png)

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

![statesWFIlter](https://user-images.githubusercontent.com/28805723/211792905-f060dacb-67bc-4220-9943-f7572eb685ee.png)

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

![cityWFIlter](https://user-images.githubusercontent.com/28805723/211793000-88dceb78-160b-471f-aa98-4a50d330da3a.png)

To get all cities of specific country with filters use `getCities` function:

```js
const getCities = async (country,state,filter) => console.log(await hawqal.getCities(country,state,filter));
getCities('finland','',{
  state_id:false,
  state_name:false
});
//first: country
//second: state
//third:  filter
```

<span style="font-weight:bold;"> Success Response</span>

![citiesCountryWFILTER](https://user-images.githubusercontent.com/28805723/211793089-4b7aeb0f-f63b-4098-b005-8aa1cec215ae.png)

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

![cityStateWFILTER](https://user-images.githubusercontent.com/28805723/211793156-ef170ca5-5fe1-43a3-b546-86a860ec0ad7.png)

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

![citiesCSWFILTER](https://user-images.githubusercontent.com/28805723/211793208-329cfad4-9e0f-4580-81c0-9d207f63a60b.png)

<span style="font-weight:bold;"> Error Response</span>

```js
[];
```

Db connection Error!!!

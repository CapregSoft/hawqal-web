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

![countryPackistanWOFILTER](https://user-images.githubusercontent.com/28805723/211772509-962aab93-e085-4ef1-841d-aa4598d56d0d.png)


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

![countryPackistanWFILTER](https://user-images.githubusercontent.com/28805723/211772986-b2a8524e-b5cd-4dba-ad07-c9dccbfc9b3b.png)


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

![countriesWFILTER](https://user-images.githubusercontent.com/28805723/211773831-7958ce2b-1314-402c-ab5b-1f2340f00a6a.png)

#### States

To get state without filters, use the `getState` function:

```js
const getState = async (state) => console.log(await hawqal.getState(state));
getState('punjab');
```

<span style="font-weight:bold;"> Success Response</span>

![stateWOFILTER](https://user-images.githubusercontent.com/28805723/211774499-c3cefb11-c95a-4190-9ba0-412d9be3b636.png)


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

![stateWFILTER](https://user-images.githubusercontent.com/28805723/211774555-dece10d3-4839-476c-aa72-3eb8a1acadf7.png)


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

![statesWFIlter](https://user-images.githubusercontent.com/28805723/211774859-5b68702f-f4d6-45b7-95a6-da48c66e2211.png)


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

![cityWFIlter](https://user-images.githubusercontent.com/28805723/211774997-fcdf4ff3-94a7-458d-b8b6-58bc16d0f536.png)


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

![citiesCountryWFILTER](https://user-images.githubusercontent.com/28805723/211775158-2efa9b2c-178b-49cc-a046-743eea520bb1.png)


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

![cityStateWFILTER](https://user-images.githubusercontent.com/28805723/211775218-d03268f5-9233-420a-ba48-e08c3ad16444.png)

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

![citiesCSWFILTER](https://user-images.githubusercontent.com/28805723/211775335-20fb01e5-07f1-4e3f-beae-15d6add996ea.png)


<span style="font-weight:bold;"> Error Response</span>

```js
[];
```

Db connection Error!!!

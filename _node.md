# Hawqal

This package contains the data of the world's countries, states, and their cities' names.

## Functionalities

- Get all countries
- Get states by country
- Get cities by country
- Get cities by state

## Installation

To install Hawqal, run the following command:

```javascript
npm i @capregsoft/hawqal
```
## Usage/Examples

### All Countries

To get a list of all countries, use the `getAllCountries` function:

```javascript
const worldData = require('@capregsoft/hawqal')
const getCountries = async () => {
  console.log(await worldData.getAllCountries());
}
getCountries();
```
### Success Response

```javascript
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
### Error Response
```javascript
{ data: [] }
```

### States By Country Name

To get a list of states for a specific country, use the `getAllStatesByCountryName` function:

```javascript
const worldData = require('@capregsoft/hawqal')
const getStates = async () => {
  console.log(await worldData.getAllStatesByCountryName('pakistan'));
}
getStates();
```

Use `async` and `await` to get a meaningful response.


### Cities By State Name & Cities by Country Name

To get a list of cities for a specific state, use the `getCitiesByStateName` function:

```javascript
const worldData = require('@capregsoft/hawqal')
const getCities = async () => {
  console.log(await worldData.getCitiesByStateName('punjab'));
}
getCities();
```






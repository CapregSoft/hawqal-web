<span style="font-size:40px;">Node Js</span>

### Installation

To install Hawqal, run the following command:

```code
npm i @capregsoft/hawqal
```

### Functions

- `Get Countries`
- `Get Cities`
- `Get States`


### Usage/Examples
Use `Asyc` and `await` to get meaningful response
#### All Countries


To get a list of all countries, use the `getCountries` function:

```code
const worldData = require('@capregsoft/hawqal')
const getData = async () =>{
    console.log(await worldData.getCountries());
}
getData();
```
 <span style="font-weight:bold;"> Success Response</span>
```
 [
  'Afghanistan',
  'Aland Islands',
  'Albania',
  'Algeria',
  'American Samoa',
  'Andorra',
  'Angola',
  'Anguilla',...
]
```


#### All States

To get a list of all countries, use the `getStates` function:

```code
const worldData = require('@capregsoft/hawqal')
const getStates = async () =>{
    console.log(await await index.getStates('pakistan'));
}
getStates();
```
 <span style="font-weight:bold;"> Success Response</span>
```
[
  'Azad Kashmir',
  'Balochistan',
  'Federally Administered Tribal Areas',
  'Gilgit-Baltistan',
  'Islamabad Capital Territory',
  'Khyber Pakhtunkhwa',
  'Punjab',
  'Sindh'
]
```
#### Cities By State & Country Name

To get a list of cities for a specific state or country, use the `getCities` function:

```code
const worldData = require('@capregsoft/hawqal')
const getCities = async () =>{
     //get all cities
    console.log(await await index.getCities());
    //get state cities
    console.log(await await index.getCities('','punjab'));
    //get country cities
    console.log(await await index.getCities('pakistan'));
    //get country,state cities
    console.log(await await index.getCities('pakistan','punjab'));
}
getCities();
```
 <span style="font-weight:bold;"> Success Response</span>
```
[
  'Fatehgarh Sahib', 'Firozpur',     'Firozpur District',
  'Fazilka',         'Gardhiwala',   'Garhshankar',
  'Ghanaur',         'Giddarbaha',   'Gurdaspur',
  'Guru Har Sahai',  'Hariana',      'Hoshiarpur',
  'Hajipur',         'Jagraon',      'Jaito',
]
```

 <span style="font-weight:bold;"> Error Response</span>
```code
[]
Db connection Error!!!
```
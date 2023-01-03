
# Python

To install the package in Python, run the following command:

### Installation

- windows
    ```python
    pip install hawqal
    ```
- macos/linux
    ```python
    pip3 install hawqal
    ```
- Latest version
    ```python
    pip install --upgrade hawqal
    ```

### Functions

- `getCountries( )`
- `getCities()`
- `getStates()`

## Usage/Example
### Countries Module
- #### Returns List of Countries

```python
   import hawqal
   hawqal.getCountries()
```
- Success Response
    ```python
    ['Afghanistan', 'Aland Islands', 'Albania', 'Algeria',...]
    ```
- #### Returns True Attributes of Countries

```python
   import hawqal
   hawqal.getCountries({"coordinates":True,"currency":True,"region":False})
```
- Success Response
    ```python
    ['Pakistan', '30', '70', 'PKR', 'Pakistani rupee', '₨']
    ```
### Cities Module
- #### Returns List of Cities

```Python
   import hawqal
   hawqal.getCities()
```
- Success Response
    ```python
    ['Islamabad','Karachi','Dehli','Mumbai',...]
    ```
- #### Returns Cities By Country

```Python
   import hawqal
   hawqal.getCities("pakistan")
```
- Success Response
    ```python
    ['Abbottabad', 'Adilpur', 'Ahmadpur Sial',...]
    ```
- #### Returns Cities By States

```Python
   import hawqal
   hawqal.getCities("arizona")
```
- Success Response
    ```python
    ['Ahwatukee Foothills', 'Ajo', 'Alhambra',...]
    ```

- #### Returns True Attributes of Cities

```Python
   import hawqal
   hawqal.getCities("arizona",{"coordinates":True})
```
- Success Response
    ```python
    [
        ['Ahwatukee Foothills', '33.34171', '-111.98403'],
        ['Ajo', '32.37172', '-112.86071'],
        ['Alhambra', '33.49838', '-112.13432'],...
    ]
    ```
### States Module
- #### Returns List of States

```python
  import hawqal
  hawqal.getStates()
```
- Success Response
```python
   ['Alabama', 'Alaska', 'American Samoa', 'Arizona',...]
```
- #### Returns States By Country

```python
  import hawqal
  hawqal.getStates()
```
- Success Response
```python
   ['Azad Kashmir', 'Balochistan', 'Federally Administered Tribal Areas', 'Gilgit-Baltistan', 'Islamabad Capital Territory',...]
```
- #### Returns True Attributes of States

```python
  import hawqal
  hawqal.getStates("pakistan",{"coordinates":True})
```
- Success Response
```python
   [
       ['Azad Kashmir', '33.9259055', '73.7810334'],
       ['Balochistan', '28.4907332', '65.0957792'],...
   ]
```

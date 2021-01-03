# Currency exchange rates API

- Learned how to interact with a simple [currency exchange rates API](https://exchangeratesapi.io/) using python
- Explored different types of endpoints and responses of the API
- Created a simple currency converter using the API at the end



```python
import requests
import json

url = 'https://api.exchangeratesapi.io/latest'
response = requests.get(url)
```

### Status code


```python
response.status_code
```




    200



### Is the request successful?


```python
response.ok
```




    True



### Content of the response in text format


```python
response.text
```




    '{"rates":{"CAD":1.5633,"HKD":9.5142,"ISK":156.1,"PHP":59.125,"DKK":7.4409,"HUF":363.89,"CZK":26.242,"AUD":1.5896,"RON":4.8683,"SEK":10.0343,"IDR":17240.76,"INR":89.6605,"BRL":6.3735,"RUB":91.4671,"HRK":7.5519,"JPY":126.49,"THB":36.727,"CHF":1.0802,"SGD":1.6218,"PLN":4.5597,"BGN":1.9558,"TRY":9.1131,"CNY":8.0225,"NOK":10.4703,"NZD":1.6984,"ZAR":18.0219,"USD":1.2271,"MXN":24.416,"ILS":3.9447,"GBP":0.89903,"KRW":1336.0,"MYR":4.934},"base":"EUR","date":"2020-12-31"}'



### Content of the response in bytes format


```python
response.content
```




    b'{"rates":{"CAD":1.5633,"HKD":9.5142,"ISK":156.1,"PHP":59.125,"DKK":7.4409,"HUF":363.89,"CZK":26.242,"AUD":1.5896,"RON":4.8683,"SEK":10.0343,"IDR":17240.76,"INR":89.6605,"BRL":6.3735,"RUB":91.4671,"HRK":7.5519,"JPY":126.49,"THB":36.727,"CHF":1.0802,"SGD":1.6218,"PLN":4.5597,"BGN":1.9558,"TRY":9.1131,"CNY":8.0225,"NOK":10.4703,"NZD":1.6984,"ZAR":18.0219,"USD":1.2271,"MXN":24.416,"ILS":3.9447,"GBP":0.89903,"KRW":1336.0,"MYR":4.934},"base":"EUR","date":"2020-12-31"}'



### Content of the response in JSON format


```python
response.json()
```




    {'rates': {'CAD': 1.5633,
      'HKD': 9.5142,
      'ISK': 156.1,
      'PHP': 59.125,
      'DKK': 7.4409,
      'HUF': 363.89,
      'CZK': 26.242,
      'AUD': 1.5896,
      'RON': 4.8683,
      'SEK': 10.0343,
      'IDR': 17240.76,
      'INR': 89.6605,
      'BRL': 6.3735,
      'RUB': 91.4671,
      'HRK': 7.5519,
      'JPY': 126.49,
      'THB': 36.727,
      'CHF': 1.0802,
      'SGD': 1.6218,
      'PLN': 4.5597,
      'BGN': 1.9558,
      'TRY': 9.1131,
      'CNY': 8.0225,
      'NOK': 10.4703,
      'NZD': 1.6984,
      'ZAR': 18.0219,
      'USD': 1.2271,
      'MXN': 24.416,
      'ILS': 3.9447,
      'GBP': 0.89903,
      'KRW': 1336.0,
      'MYR': 4.934},
     'base': 'EUR',
     'date': '2020-12-31'}



### JSON content is in the form of a python dictionary


```python
type(response.json())
```




    dict



### JSON content in the form of a string with neat indentation

json.dumps() --------> Python to JSON  
json.loads() --------> JSON to Python


```python
print(json.dumps(response.json(), indent=4))
```

    {
        "rates": {
            "CAD": 1.5633,
            "HKD": 9.5142,
            "ISK": 156.1,
            "PHP": 59.125,
            "DKK": 7.4409,
            "HUF": 363.89,
            "CZK": 26.242,
            "AUD": 1.5896,
            "RON": 4.8683,
            "SEK": 10.0343,
            "IDR": 17240.76,
            "INR": 89.6605,
            "BRL": 6.3735,
            "RUB": 91.4671,
            "HRK": 7.5519,
            "JPY": 126.49,
            "THB": 36.727,
            "CHF": 1.0802,
            "SGD": 1.6218,
            "PLN": 4.5597,
            "BGN": 1.9558,
            "TRY": 9.1131,
            "CNY": 8.0225,
            "NOK": 10.4703,
            "NZD": 1.6984,
            "ZAR": 18.0219,
            "USD": 1.2271,
            "MXN": 24.416,
            "ILS": 3.9447,
            "GBP": 0.89903,
            "KRW": 1336.0,
            "MYR": 4.934
        },
        "base": "EUR",
        "date": "2020-12-31"
    }
    

### keys in the json object


```python
response.json().keys()
```




    dict_keys(['rates', 'base', 'date'])



### url specifying symbols required 


```python
url_with_symbols = f"{url}?symbols=USD,GBP"
response = requests.get(url_with_symbols)
```


```python
response
```




    <Response [200]>




```python
data = response.json()
```


```python
data['base']
```




    'EUR'




```python
data['date']
```




    '2020-12-31'




```python
data['rates']
```




    {'USD': 1.2271, 'GBP': 0.89903}



### url specifying both base and symbols required


```python
url_with_symbols_and_base = f"{url}?symbols=INR,GBP,EUR&base=USD"
response = requests.get(url_with_symbols_and_base)
```


```python
response.json()
```




    {'rates': {'INR': 73.0669872056, 'EUR': 0.8149295086, 'GBP': 0.7326460761},
     'base': 'USD',
     'date': '2020-12-31'}




```python
# 1 dollar in rupees
round(response.json()['rates']['INR'], 2)
```




    73.07



### obtaining historical exchange rates


```python
base_url = 'https://api.exchangeratesapi.io'
date = '2016-01-26'
historical_url = f"{base_url}/{date}"

response = requests.get(historical_url)
response.status_code
```




    200




```python
print(json.dumps(response.json(), indent=4))
```

    {
        "rates": {
            "CAD": 1.5411,
            "HKD": 8.4498,
            "SGD": 1.5498,
            "PHP": 52.051,
            "DKK": 7.4622,
            "HUF": 312.73,
            "CZK": 27.021,
            "AUD": 1.555,
            "RON": 4.5348,
            "SEK": 9.2644,
            "IDR": 15004.76,
            "INR": 73.5797,
            "BRL": 4.4465,
            "RUB": 86.7725,
            "HRK": 7.6658,
            "JPY": 128.22,
            "THB": 38.865,
            "CHF": 1.1008,
            "PLN": 4.4942,
            "BGN": 1.9558,
            "TRY": 3.2699,
            "CNY": 7.1314,
            "NOK": 9.4858,
            "NZD": 1.6777,
            "ZAR": 17.8881,
            "USD": 1.0837,
            "MXN": 20.1259,
            "ILS": 4.3084,
            "GBP": 0.76095,
            "KRW": 1303.82,
            "MYR": 4.6335
        },
        "base": "EUR",
        "date": "2016-01-26"
    }
    

### extracting data for a certain period of time


```python
start_date = '2017-04-26'
end_date = '2018-04-26'
symbols = 'GBP'
time_period = f"{base_url}/history?start_at={start_date}&end_at={end_date}&symbols={symbols}"

response = requests.get(time_period)
response.status_code
```




    200



the api returns dates in random order  
to sort it we need to use sort_keys=True.

### format  
#### base:  
#### end_at:  
#### rates:  
##### &nbsp; date:  
###### &nbsp; &nbsp; currency-rate  
#### start_at


```python
print(json.dumps(response.json(), indent=4, sort_keys=True))
```

    

### Invalid request
In the date, the month is written as 13, which is invalid.  
The server responds with a status code of 400 which stands for a client error of a bad request.


```python
base_url = 'https://api.exchangeratesapi.io'
date = '2020-13-01'
invalid_url = f"{base_url}/{date}"

response = requests.get(invalid_url)
response.status_code
```




    400




```python
response.json()
```




    {'error': "time data '2020-13-01' does not match format '%Y-%m-%d'"}



The base is USB instead of USD


```python
base_url = 'https://api.exchangeratesapi.io'
invalid_url = f"{base_url}/latest/?base=USB"

response = requests.get(invalid_url)
response.status_code
```




    400




```python
response.json()
```




    {'error': "Base 'USB' is not supported."}



### Simple currency converter


```python
date = input(
    "Please enter the date in yyyy-mm-dd format or 'latest' if you want latest rates:\n")
base = input("Convert from currency:\n").upper()
currency = input("Convert to currency:\n").upper()
amount = float(input(f"How many {base} do you want to convert?:\n"))

url = f"https://api.exchangeratesapi.io/{date}?base={base}&symbols={currency}"
response = requests.get(url)

if response.ok is False:
    print(f"\nError:{response.status_code}\n")
    print(f"Error message: {response.json()['error']}")
else:
    data = response.json()
    rate = data['rates'][currency]
    result = amount * rate

    print(f"{amount} {base} = {round(result,3)} {currency} on {data['date']}")
```

    Please enter the date in yyyy-mm-dd format or 'latest' if you want latest rates:
    latest
    Convert from currency:
    usd
    Convert to currency:
    inr
    How many USD do you want to convert?:
    100
    100.0 USD = 7306.699 INR on 2020-12-31
    


```python

```

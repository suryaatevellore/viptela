# Viptela
Python library for use with Viptela vManage API.  
Requires [requests](http://docs.python-requests.org/en/master/)


[![Build Status](https://travis-ci.org/bobthebutcher/netconnect.svg?branch=master)](https://travis-ci.org/bobthebutcher/viptela)
[![Coverage Status](https://coveralls.io/repos/github/bobthebutcher/viptela/badge.svg?branch=master)](https://coveralls.io/github/bobthebutcher/viptela?branch=master) 

### About
[Viptela](http://viptela.com/) is an SD-WAN vendor with a solid rest API. 
The API is documented on the vManage host and can be found by going to 
`https://vmanage-hostname:port/apidocs`. Additional API documentation can be 
found on the viptela site support portal `http://viptela.com/support/` (login required)


### Installation
```bash
cd ~/envs
virtualenv viptela-test
source viptela-test/bin/activate
pip install https://github.com/bobthebutcher/viptela/archive/master.zip
```

### Instantiate a connection to a vManage device
```python
from viptela.viptela import Viptela
v = Viptela(user='admin', user_pass='admin', vmanage_server='10.1.1.41')
```

### Call methods
```python
devs = v.get_all_devices()
```

### Returned Result
All methods return a Result named tuple with the `requests.json()` data in the `data` element.  
The complete `requests.response` object is stored in the `response` element
```python
Result(ok=True, status_code=200, error='', reason='Success', data={}, response=<Response [200]>)
```

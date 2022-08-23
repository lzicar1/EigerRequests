# Eiger Requests

A repository implementing example Python http requests for DECTRIS EIGER DETECTOR. Based on SIMPLON API reference (see the pdf file attached in this repo). The working Python 3 examples are in requests.ipynb. This repository is not official.


## SIMPLON Example
- see page 16 of the reference
- the following example is in Python 2 

```python
import json
# Imports "JSON" library
import requests
# Imports "requests" library
dict_data = {'value':8040.0}
# Prepare the dictionary (a "value" with the value 8040.0)
data_json = json.dumps(dict_data)
# Convert the dictionary to JSON
r = requests.put('http://<address_of_dcu>/detector/api/<version>/config/photon_energy', data
=data_json)
# Execute the request on the config value "photon_energy" (REPLACE <ADDRESS_of_DCU> and <
    VERSION> with the values of YOUR system)
print r.status_code
# Print the http status code (NOTE: Only http code 200 is OK, everything else is an error)
print r.json()
# Print the returned JSON string. (Containing the names of the subsequently changed values)
```
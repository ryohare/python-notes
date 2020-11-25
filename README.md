# python-notes
Notes on python software dev of stuff I always end up googling over and over again.

## Logging HTTP Requests in Requests Library
To debug requests in the [requests](https://requests.readthedocs.io/en/master/_modules/requests/api) logging can be enabled to capture the raw request w/o the need of a MITM proxy.

```python
# import logging and http_client class
import logging
import http.client as http_client

# initialize logger - add to __init__ for a class or just to the top of a classless file
http_client.HTTPConnection.debuglevel = 1
logging.basicConfig()
logging.getLogger().setLevel(logging.DEBUG)
requests_log = logging.getLogger("requests.packages.urllib3")
requests_log.setLevel(logging.DEBUG)
requests_log.propagate = True
```

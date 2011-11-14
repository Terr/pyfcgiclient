pyfcgiclient
============

A Python client interface to FastCGI servers.

This code is mostly modified code found in the [ZTC] project on BitBucket, which in turn is based on code from [flup].

Please note that this is still very much a WIP. Any comments and patches are welcome.

Example
-------
```python
from pyfcgiclient.fpm import FPM

phpfpm = FPM(
    host=getattr(settings, 'FPM_HOST', '127.0.0.1'),
    port=getattr(settings, 'FPM_PORT', 9000),
    document_root='/var/www/'
)

post_string = 'title=Hello&body=World!'

status_header, headers, output, error_message = phpfpm.load_url(
    url='/index.php?a=b',
    content=post_string,
    remote_addr='192.0.43.10',
    cookies='c=d;e=f;'
)
```

TODO
----
* Create setup
* Fix unicode/ASCII errors


[flup]: http://trac.saddi.com/flup
[ZTC]: https://bitbucket.org/rvs/ztc/

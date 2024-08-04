```python
import logging.config
import os

if os.path.exists('logging.conf'): # prod
    logging.config.fileConfig('logging.conf')
else: # dev, ~/.django.logging.conf
    path = os.path.join(os.environ['HOME'],'.django.logging.conf')
    if os.path.exists(path):
        logging.config.fileConfig(path)
```

`docker-compose.prod.xml`
```xml
services:
  service_name:
    environment:
      - LOG_FILE=/var/log/XXX.log
    volumes:
      - /root/logging.conf:/code/logging.conf
```

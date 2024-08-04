```python
import logging.config
import os

if os.path.exists('logging.conf'):
    logging.config.fileConfig('logging.conf')
```

`docker-compose.prod.xml`
```xml
services:
  service_name:
    volumes:
      - /root/logging.conf:/code/logging.conf
```

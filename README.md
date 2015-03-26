Flask-Cache

Added fallback cache.
If the first configured cache fails (e.g., redis server becomes unreachable) the fallback configured cache is used (e.g., filesystem)

In order to configure the fallback cache a new dictionary can be used:

```python
cache = Cache(app, config={'CACHE_TYPE': 'redis','CACHE_DEFAULT_TIMEOUT': 600}, fallback_config={'CACHE_TYPE':'filesystem','CACHE_DIR':'/tmp/fc'})
```
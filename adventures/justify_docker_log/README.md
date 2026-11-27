### Justify Docker Log

```yaml
x-logging: &logging
  driver: json-file
  options: {max-size: "10m", max-file: "3"}
```

```yaml
services:
  db:
    logging: *logging
  redis:
    logging: *logging
```

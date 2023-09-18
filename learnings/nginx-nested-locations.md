# Nginx Nested Locations

```
server {
  location /app {
    location /app/assets {
      # ...
    }
    
    location /app/pages {
      # ...
    }
  }
}
```

Nested locations are not relative to the parent location. 

- `location /app` parent location block that matches requests starting with `/app`.
- `location/app/assets` nested location that matches `/app/assets`.
- `location/app/pages` nested location that matches `/app/pages`.

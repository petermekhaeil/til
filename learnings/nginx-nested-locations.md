# Nginx Nested Locations

Nginx supports nested locations:

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

Note that nested locations are not relative to the parent location. 

In the above example:
- `location /app` parent location block that matches requests starting with `/app`.
- `location/app/assets` nested location that matches `/app/assets`.
- `location/app/pages` nested location that matches `/app/pages`.

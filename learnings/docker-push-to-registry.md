# Push Docker image to self-hosted registry

Steps on building a Docker image and pushing it to a self-hosted registry:

1. Build the Docker image using `docker build`. 
2. Run `docker login` to log in to the registry.
3. Tag the image to the registry using `docker tag`.
4. Push the image to the registry using  `docker push`.

Putting it together in an example:

```bash
# Build the image
docker build -t app:1.0.0 .

# Log into the registry
docker login example.com

# Tag the image to the registry
docker tag app:1.0.0 example.com/app:1.0.0

# Push the image to the registry
docker push example.com/app:1.0.0
```

This will create an image with the name `example.com/app:1.0.0` being pushed to the registry.

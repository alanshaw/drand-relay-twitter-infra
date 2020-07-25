# drand-relay-twitter-infra

Infrastructure for [drand-relay-twitter](https://github.com/drand/drand-relay-twitter).

## Usage

See [kubernetes deployment instructions](./k8s/README.md).

### Publish a new Docker image

```sh
# Clone the rleay project
git clone https://github.com/drand/drand-relay-twitter.git
cd drand-relay-twitter

# Build your container
docker build -t drand-relay-twitter .

# Get it to run
docker run drand-relay-twitter

# Commit new version
docker commit -m="some commit message" <CONTAINER_ID> alanshaw/drand-relay-twitter

# Push to docker hub (must be logged in, do docker login)
docker push alanshaw/drand-relay-twitter
```

## Contribute

Feel free to dive in! [Open an issue](https://github.com/alanshaw/drand-relay-twitter-infra/issues/new) or submit PRs.

## License

[MIT](LICENSE) © Alan Shaw

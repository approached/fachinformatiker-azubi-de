# Fachinformatiker Azubi

This website is built using [Docusaurus 2](https://docusaurus.io/), a modern static website generator.

### Installation

```
$ yarn
```

### Local Development

```
$ yarn start
```

This command starts a local development server and opens up a browser window. Most changes are reflected live without having to restart the server.

Test local docker container
```sh
yarn build
docker-compose -f docker-compose-local.yml up
```

### Build

```
$ yarn build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

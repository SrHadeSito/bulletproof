## Development

We use `node` version `14.9.0`

```
nvm install 14.9.0
```

```
nvm use 14.9.0
```

The first time, you will need to run

```
npm install
```

Then just start the server with

```
npm run start
```
It uses nodemon for livereloading :peace-fingers:

## Online one-click setup

You can use Gitpod for the one click online setup. With a single click it will launch a workspace and automatically:

- clone the `bulletproof-nodejs` repo.
- install the dependencies.
- run `cp .env.example .env`.
- run `npm run start`.

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/from-referrer/)

# API Validation

 By using [celebrate](https://github.com/arb/celebrate), the req.body schema becomes cleary defined at route level, so even frontend devs can read what an API endpoint expects without needing to write documentation that can get outdated quickly.

 ```js
 route.post('/signup',
  celebrate({
    body: Joi.object({
      name: Joi.string().required(),
      email: Joi.string().required(),
      password: Joi.string().required(),
    }),
  }),
  controller.signup)
 ```

 **Example error**

 ```json
 {
  "errors": {
    "message": "child \"email\" fails because [\"email\" is required]"
  }
 }
 ```

[Read more about celebrate here](https://github.com/arb/celebrate) and [the Joi validation API](https://github.com/hapijs/joi/blob/v15.0.1/API.md)

# Roadmap
- [x] API Validation layer (Celebrate+Joi)
- [ ] Unit tests examples
- [x] The logging _'layer'_
- [ ] Add agenda dashboard
- [x] Continuous integration with CircleCI 😍
- [ ] Deploys script and docs for AWS Elastic Beanstalk and Heroku
- [ ] Integration test with newman 😉
- [ ] Instructions on typescript debugging with VSCode

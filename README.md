## Installation

1. **Clone the repository:**

    ```sh
    git clone https://github.com/Rjain4488/RemCodeChallenge.git
    cd RemCodeChallenge
    ```

2. **Install dependencies:**

    ```sh
    npm install
    ```

3. **Install Playwright Browsers:**

    ```sh
    npx playwright install --with-deps
    ```


## Environment Variables

The framework uses `.env` files for managing environment-specific variables. Create a folder `env/` in the root directory and add `.env.{environmentName}` files. Example for `.env.dev`:

```
# .env.dev
URL=https://conduit.bondaracademy.com/
API_URL=https://conduit-api.bondaracademy.com/
USER_NAME={your username}
EMAIL={your email}
PASSWORD={your password}
```

The default environment name should be DEV (.env.dev). The script is built to use the file if `process.env.VARIABLE_NAME` is `undefined`.

These variables can be accessed in your tests and page objects using `process.env.VARIABLE_NAME`.

To set desired environment, run the following command into terminal, before starting the tests:

```
$env:ENVIRONMENT='{environmentName}'
```

You can verify the set variable with:

```sh
echo $env:ENVIRONMENT
```

## Project Structure

```
RemCodeChallenge/
├── .github/
|   └── workflows
│       ├── playwright-container.yml
│
├── env/
│   └── .env.dev
│
├── fixture/
│   ├── api
│   |   ├── api-request-fixture.ts
│   |   ├── plain-function.ts
│   |   ├── schemas.ts
│   |   └── types-guards.ts
│   └── pom
│       ├── page-object-fixture.ts
│       └── test-options.ts
|
├── pages/
│   └── clientSite/
|       ├── articlePage.ts
|       ├── homePage.ts
|       └── navPage.ts
|
├── tests-data/
│   ├── articleData.json
│   └── invalidCredentials.json
|
├── tests/
│   ├── auth.setup.ts
│   ├── API/
│   |   ├──article.spec.ts
│   |   └──authentication.spec.ts
|   |
│   └── ClientSite/
│       ├──article.ts
│       ├──home.spec.ts
│       └──nav.spec.ts
|
├── .gitignore
├── .prettierrc
├── package-lock.json
├── package.json
├── playwright.config.ts
└── README.md
```


## Running Tests Locally

To run tests, use the following commands (defined in the `scripts` section of `package.json`):

```sh
npm run test        # Run all tests
npm run smoke       # Run smoke tests
npm run sanity      # Run sanity tests
npm run api         # Run API tests
npm run regression  # Run regression tests
npm run fullTest    # Run the full test suite
```

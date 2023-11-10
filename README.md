# Nast - Nuxt 3 & FastApi

Look at the [Nuxt 3 documentation](https://nuxt.com/docs/getting-started/introduction) to learn more.

Look at the [FastApi documentation](hhttps://fastapi.tiangolo.com/) to learn more.

This project uses FastApi for the backend and Nuxt 3 for the frontend.



## Setup FRONTEND

Make sure to install the dependencies:

```bash
cd frontend

npm install

npm run dev
```
This starts the backend server on `http://localhost:3000`.



## Setup BACKEND

Make sure to install the dependencies:

```bash
cd backend

pip install requirements.txt

pip install requirements-dev.txt

uvicorn app.main:app --reload
```
This starts the backend server on `http://localhost:8000`.


-----



## Development Server

Start the development server on `http://localhost:8000`:

```bash
# npm
npm run dev

# pnpm
pnpm run dev

# yarn
yarn dev

# bun
bun run dev
```

## Production

Build the application for production:

```bash
# npm
npm run build

# pnpm
pnpm run build

# yarn
yarn build

# bun
bun run build
```

Locally preview production build:

```bash
# npm
npm run preview

# pnpm
pnpm run preview

# yarn
yarn preview

# bun
bun run preview
```

Check out the [deployment documentation](https://nuxt.com/docs/getting-started/deployment) for more information.

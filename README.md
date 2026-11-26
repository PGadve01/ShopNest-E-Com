# ShopNest

ShopNest is a MERN e-commerce project with a React frontend and an Express/MongoDB backend.

## Requirements

- Node.js and npm
- MongoDB running locally, or a MongoDB connection string
- Cloudinary credentials if you want to upload product images

## Install

From the project root:

```powershell
npm run install-all
```

## Configure environment

Copy `backend/.env.example` to `backend/.env`, then set the values for your machine and services. Keep the real `.env` file private; it is ignored by Git.


Set a private `JWT_SECRET`. Configure Cloudinary, email, or payment credentials only if you use those features. Never put backend credentials in frontend files or commit them to GitHub.



## Run in development

Start MongoDB, then run from the project root:

```powershell
npm run dev
```


## Build and run as a single server

Build the React app:

```powershell
npm --prefix frontend run build
```

Then start the backend in production mode from PowerShell:

```powershell
npm start
```

The backend serves the frontend build and API on the backend port configured in `backend/.env` (default: `5001`).

## Products

The homepage requests products from `GET /api/products`. A successful empty response (`[]`) means the database has no product records yet.

Creating products requires an administrator account. The API endpoint is `POST /api/products`, authenticated with a bearer token. Submit `name`, `description`, `price`, `category`, and `stock` as form fields, and an image using the form field name `image`. Configure Cloudinary in `backend/.env` for image uploads. New registered accounts default to the regular user role; do not make role changes available publicly.

## Project layout

```text
backend/     Express API, MongoDB models, routes, and controllers
frontend/    React application
README.md    Project setup and usage
```

## GitHub and credentials

The root `.gitignore` excludes `.env` files, dependencies, build output, and local uploads while allowing `.env.example` templates. Before pushing, review the staged files and confirm no real credentials are included. If a credential was ever committed or shared, rotate it; removing it from the latest commit alone does not invalidate it.

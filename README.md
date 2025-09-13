# Micro Frontend Example

This repository demonstrates a simple micro-frontend architecture using Webpack Module Federation and React. The project is split into two independent applications:

- **mfe1**: Product Listing Application (Host)
- **mfe2**: Cart Application (Remote)

## Project Structure

```
mfe1/
  ├── src/
  │   ├── App.js
  │   ├── bootstrap.js
  │   └── index.js
  ├── public/
  │   └── index.html
  ├── package.json
  └── webpack.config.js

mfe2/
  ├── src/
  │   ├── App.js
  │   ├── bootstrap.js
  │   └── index.js
  ├── public/
  │   └── index.html
  ├── package.json
  └── webpack.config.js
```

## How It Works

- **mfe1** acts as the host application. It loads its own UI and dynamically loads the Cart Application from **mfe2** using Module Federation.
- **mfe2** exposes its `App` component as a remote module.
- Both applications use React and share dependencies to avoid duplication.

## Running Locally

1. **Install dependencies** in both `mfe1` and `mfe2`:

   ```sh
   cd mfe1
   npm install
   cd ../mfe2
   npm install
   ```

2. **Start both applications** in separate terminals:

   ```sh
   # Terminal 1
   cd mfe1
   npm start

   # Terminal 2
   cd mfe2
   npm start
   ```

3. **Access the applications:**
   - Product Listing (host): http://localhost:3001
   - Cart Application (remote): http://localhost:3002

## Key Features

- **Module Federation**: mfe1 loads mfe2’s `App` component at runtime.
- **React**: Uses modern React features and best practices.
- **Isolated Development**: Each app can be developed and deployed independently.

## File Highlights

- `mfe1/webpack.config.js`: Configures mfe1 as a host and sets up remote loading of mfe2.
- `mfe2/webpack.config.js`: Exposes the Cart Application as a remote module.
- `mfe1/src/App.js`: Imports and renders the remote Cart Application.
- `mfe2/src/App.js`: Simple Cart Application UI.

## License

This project is licensed under the ISC License.

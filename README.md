
# My Wails Frontend Project

This is a desktop application built with [Wails](https://wails.io/), a framework for creating lightweight desktop apps using Go and web technologies. The frontend is powered by [Vite](https://vitejs.dev/) for fast development and optimized builds, with TypeScript for type-safe JavaScript development.

## Prerequisites

Before you begin, ensure you have the following installed:

- **Go**: Version 1.24.1 or higher (required for Wails backend)
- **Node.js**: Version 18+ or 20+ (required by Vite 6.2.0)
- **Wails CLI**: Version 2.10.1
- **npm**: Comes with Node.js, used to manage frontend dependencies
- **TypeScript**: Version ~5.7.2 (installed via npm)

To check your versions:
```bash
go version
node -v
wails version
npm -v
tsc -v
```

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/darkb0ts/Wails-vite-ts-tailwindcss-shadcn-template.git
   cd Wails-vite-ts-tailwindcss-shadcn-template.git
   ```

2. **Install Wails CLI (if not already installed)**
   ```bash
   go install github.com/wailsapp/wails/v2/cmd/wails@v2.10.1
   ```

3. **Install Frontend Dependencies**
   Navigate to the `frontend` directory and install the required packages:
   ```bash
   cd frontend
   npm install
   ```

   This will install Vite 6.2.0, TypeScript 5.7.2, and other dependencies listed in `package.json`.

4. **Verify Setup**
   Run the following to ensure Wails can detect your environment:
   ```bash
   wails doctor
   ```

## Project Structure

```
my-wails-project/
├── build/             # Build artifacts and platform-specific files
├── frontend/          # Frontend source code
│   ├── src/           # TypeScript source files
│   ├── public/        # Static assets
│   ├── index.html     # Entry point for the frontend
│   ├── package.json   # Node.js dependencies and scripts
│   ├── vite.config.ts # Vite configuration
│   └── tsconfig.json  # TypeScript configuration
├── go.mod             # Go module dependencies
├── main.go            # Go entry point for the Wails app
└── wails.json         # Wails project configuration
```

## Development

1. **Start the Development Server**
   From the project root, run:
   ```bash
   wails dev
   ```
   This launches the app in development mode with hot-reloading enabled via Vite. The frontend will be served at `http://localhost:34115` by default.

2. **Edit the Frontend**
   Modify files in `frontend/src/` (e.g., `main.ts`) to update the UI. Changes will reflect instantly thanks to Vite's hot module replacement (HMR).

3. **Backend Integration**
   Bind Go functions to the frontend by editing `main.go`. These will be accessible in TypeScript via the `wailsjs` bindings generated automatically in `frontend/wailsjs/`.

## Building the Application

To create a production-ready binary:
```bash
wails build
```
The output will be in `build/bin/`, named after your project (e.g., `myapp` on Windows, macOS, or Linux).

## Configuration

- **Vite**: Configured in `frontend/vite.config.ts`. Adjust settings like port or base URL if needed.
- **TypeScript**: Configured in `frontend/tsconfig.json`. Ensure it aligns with Vite and Wails requirements.
- **Wails**: Configured in `wails.json`. Customize app name, author, and other metadata here.

## Dependencies

- **Vite**: `^6.2.0`
- **Node.js**: `18+` or `20+`
- **Wails CLI**: `v2.10.1`
- **TypeScript**: `~5.7.2`

See `frontend/package.json` for additional frontend dependencies.

## Troubleshooting

- **Vite Errors**: Ensure Node.js is version 18+ or 20+. Update with `nvm install 20` if needed.
- **Wails Command Not Found**: Verify `$GOPATH/bin` is in your PATH (`export PATH=$PATH:$GOPATH/bin`).
- **TypeScript Issues**: Check `tsconfig.json` and ensure all paths resolve correctly.

## Contributing

Feel free to submit issues or pull requests to improve this project!

## License

This project is licensed under the [MIT License](LICENSE).

---
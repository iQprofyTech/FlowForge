diff --git a/README.md b/README.md
index 62c6fe373e21a8d085d6fa0f09a84c9433ee9e2a..8d9c7d78a3edc80741136f595c7a3a58070a396f 100644
--- a/README.md
+++ b/README.md
@@ -1,2 +1,70 @@
 # FlowForge
+
 FlowForge - weave 12
+
+## Prerequisites
+
+- Node.js 18+
+- npm
+- Docker (optional for containerised deployment)
+
+## Environment Variables
+
+| Name         | Description                       | Default |
+|--------------|-----------------------------------|---------|
+| `PORT`       | Port the HTTP server listens on   | `3000`  |
+| `DATABASE_URL` | Connection string for the database | –       |
+| `REDIS_URL`  | Optional Redis connection string  | –       |
+
+Environment variables can be placed in a `.env` file at the project root
+or exported in your shell before starting the application.
+
+## Running Locally
+
+1. Install dependencies:
+
+   ```bash
+   npm install
+   ```
+
+2. Create a `.env` file with the variables described above.
+3. Start the development server:
+
+   ```bash
+   npm run dev
+   ```
+
+   For a production-like server use:
+
+   ```bash
+   npm start
+   ```
+
+## Running in Production
+
+1. Build the application and ensure all environment variables are set:
+
+   ```bash
+   npm run build
+   NODE_ENV=production npm start
+   ```
+
+2. Alternatively, build and run using Docker:
+
+   ```bash
+   docker build -t flowforge .
+   docker run -p 3000:3000 --env-file .env flowforge
+   ```
+
+## Launching Services
+
+If the project includes additional services (e.g. databases or caches), they
+can be launched with Docker Compose:
+
+```bash
+docker compose up
+```
+
+Running the above command starts all defined services, including the
+application itself.
+

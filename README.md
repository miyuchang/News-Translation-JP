<div align="center">
<img width="1200" height="475" alt="GHBanner" src="https://github.com/user-attachments/assets/0aa67016-6eaf-458a-adb2-6e31a0763ed6" />
</div>

# Run and deploy your AI Studio app

This contains everything you need to run your app locally.

View your app in AI Studio: https://ai.studio/apps/drive/1gr-dasDXb37TJrmGEAigXRHHoAQAHEoW

## Run Locally

**Prerequisites:**  Node.js


1. Install dependencies:
   `npm install`
2. (Optional) Run the app locally for development:
   `npm run dev`

## Run with Docker

This project can be built and served with Docker Compose. By default the container serves the site on port `80`; the repository `docker-compose.yml` maps it to `9061` on the host.

1. Ensure you have a `.htpasswd` file at the project root with your HTTP basic-auth credentials. The Compose file mounts `./.htpasswd` into the container at `/etc/nginx/.htpasswd`. Example (if you have the `htpasswd` tool):

   ```bash
   htpasswd -c .htpasswd username
   ```

   If you don't want authentication, remove or change the mount in `docker-compose.yml` and `nginx.conf`.

2. Build and run (detached):

   ```bash
   docker compose up --build -d
   ```

3. Stop and remove containers:

   ```bash
   docker compose down
   ```

Access the app at: http://localhost:9061/ and the demo path at http://localhost:9061/demo/jpnews

**Note:** This repository does not require a `GEMINI_API_KEY` to run; you can ignore the GEMINI-related step from other templates.

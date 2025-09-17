# Deploy to Vercel
## Prerequisites

- Vercel CLI installed (`npm install -g vercel`)
- Logged into Vercel with Gmail account: xxxxxx@gmail.com; remind users to run ```vercel login``` to sign in as email

## Usage

```bash
/deploy
```

This command will:
1. Build the project for production
2. Deploy to Vercel
3. Provide the deployment URL

## Manual Setup (First Time)

If this is your first deployment, you may need to:

1. Install Vercel CLI globally:
   ```bash
   npm install -g vercel
   ```

2. Login to Vercel:
   ```bash
   vercel login
   ```
   Select "Continue with Email" and use: xxxxx@gmail.com

3. Deploy the project:
   ```bash
   vercel --prod
   ```
   - This will upload your local build files directly
   - No GitHub integration required for local deployment

## Build Configuration

The project uses Vite with these settings:
- Build command: `npm run build`
- Output directory: `build`
- Node.js version: 18.x

## Environment Variables

No environment variables required for this project.

---

**Command Implementation:**

```bash
#!/bin/bash

echo "=� Deploying Treasure Hunt Game to Vercel..."

# Check if Vercel CLI is installed
if ! command -v vercel &> /dev/null; then
    echo "L Vercel CLI not found. Installing..."
    npm install -g vercel
fi

# Build the project
echo "=� Building project..."
npm run build

if [ $? -ne 0 ]; then
    echo "L Build failed. Please fix build errors before deploying."
    exit 1
fi

# Deploy to Vercel
echo "< Deploying to Vercel..."
vercel --prod

echo " Deployment complete!"
echo "= Your game is now live on Vercel"
```
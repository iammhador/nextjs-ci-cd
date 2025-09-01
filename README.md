# Next.js CI/CD & PM2 Deployment Project

This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Project Purpose

This project is designed for testing **CI/CD pipelines** and **PM2 deployment** strategies. It includes:

- GitHub Actions workflow for continuous integration
- Automated testing and deployment processes
- PM2 process management for production deployment
- Best practices for Next.js application deployment

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.

## CI/CD & PM2 Deployment

### GitHub Actions Workflow

This project includes a GitHub Actions workflow (`.github/workflows/basic-checkout.yml`) that:

- Triggers on push to the main branch
- Performs basic system checks and environment setup
- Lists repository contents and system information
- Displays custom environment variables
- Runs conditional steps based on event types

### PM2 Deployment

For production deployment with PM2:

```bash
# Install PM2 globally
npm install -g pm2

# Build the Next.js application
npm run build

# Start the application with PM2
pm2 start npm --name "nextjs-app" -- start

# Monitor the application
pm2 status
pm2 logs nextjs-app

# Stop the application
pm2 stop nextjs-app

# Restart the application
pm2 restart nextjs-app
```

### Testing CI/CD Pipeline

To test the CI/CD pipeline:

1. Make changes to your code
2. Commit and push to the main branch
3. Check the Actions tab in your GitHub repository
4. Monitor the workflow execution and logs
5. Verify successful deployment

### Environment Variables

The workflow uses custom environment variables:
- `CUSTOM_MESSAGE`: Demo message for testing environment variable access

### Monitoring & Logs

- GitHub Actions logs: Available in the Actions tab of your repository
- PM2 logs: Use `pm2 logs` command to view application logs
- System monitoring: PM2 provides built-in monitoring with `pm2 monit`

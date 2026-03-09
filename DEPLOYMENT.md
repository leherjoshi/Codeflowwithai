# CodeFlow AI - Deployment Guide

## Deploy to Vercel

### Prerequisites
- GitHub account with this repository
- Vercel account (sign up at https://vercel.com)

### Deployment Steps

1. **Go to Vercel Dashboard**
   - Visit https://vercel.com/new
   - Sign in with your GitHub account

2. **Import Repository**
   - Click "Import Project"
   - Select your GitHub repository: `leherjoshi/Codeflowwithai`
   - Vercel will automatically detect it's a Next.js project

3. **Configure Project**
   - **Framework Preset**: Next.js (auto-detected)
   - **Root Directory**: `frontend` (IMPORTANT: Set this to `frontend`)
   - **Build Command**: `npm run build` (default)
   - **Output Directory**: `.next` (default)

4. **Environment Variables**
   Add the following environment variable:
   ```
   NEXT_PUBLIC_API_URL=https://n8e9ghd13g.execute-api.ap-south-1.amazonaws.com/dev
   ```

5. **Deploy**
   - Click "Deploy"
   - Wait for the build to complete (2-3 minutes)
   - Your app will be live at `https://your-project-name.vercel.app`

### Post-Deployment

1. **Test the Application**
   - Visit your Vercel URL
   - Try registering a new account
   - Test the dashboard, interview, and mentor features

2. **Custom Domain (Optional)**
   - Go to Project Settings → Domains
   - Add your custom domain
   - Follow Vercel's DNS configuration instructions

3. **Environment Variables**
   - If you need to update the API URL, go to Project Settings → Environment Variables
   - Add/update variables and redeploy

### Troubleshooting

**Build Fails:**
- Check the build logs in Vercel dashboard
- Ensure all dependencies are in `package.json`
- Verify Node.js version compatibility

**API Errors:**
- Verify `NEXT_PUBLIC_API_URL` is set correctly
- Check CORS settings on your AWS API Gateway
- Ensure JWT authorizer is working properly

**404 Errors:**
- Make sure Root Directory is set to `frontend`
- Check that all routes are properly defined in Next.js

### Monitoring

- View deployment logs in Vercel dashboard
- Check Analytics for performance metrics
- Monitor API errors in browser console

### Continuous Deployment

Vercel automatically deploys:
- **Production**: Every push to `main` branch
- **Preview**: Every pull request

To disable auto-deployment:
- Go to Project Settings → Git
- Configure deployment branches

## Local Development

```bash
cd frontend
npm install
npm run dev
```

Visit http://localhost:3000

## Support

For issues:
- Check Vercel documentation: https://vercel.com/docs
- Review Next.js documentation: https://nextjs.org/docs
- Check AWS API Gateway logs for backend issues

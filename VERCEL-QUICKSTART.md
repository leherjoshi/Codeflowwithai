# 🚀 Quick Deploy to Vercel

## Step-by-Step Guide

### 1. Go to Vercel
Visit: https://vercel.com/new

### 2. Import Your Repository
- Click "Import Git Repository"
- Select: `leherjoshi/Codeflowwithai`
- Click "Import"

### 3. Configure Build Settings
**IMPORTANT:** Set these values:

| Setting | Value |
|---------|-------|
| Framework Preset | Next.js |
| Root Directory | **`frontend`** ⚠️ |
| Build Command | `npm run build` |
| Output Directory | `.next` |

### 4. Add Environment Variable
Click "Environment Variables" and add:

```
Name: NEXT_PUBLIC_API_URL
Value: https://n8e9ghd13g.execute-api.ap-south-1.amazonaws.com/dev
```

### 5. Deploy
Click "Deploy" button and wait 2-3 minutes.

### 6. Done! 🎉
Your app will be live at: `https://your-project-name.vercel.app`

---

## Common Issues

### ❌ Build fails with "Cannot find module"
**Solution:** Make sure Root Directory is set to `frontend`

### ❌ 404 on all pages
**Solution:** Verify Root Directory is `frontend`, not empty

### ❌ API calls fail
**Solution:** Check that `NEXT_PUBLIC_API_URL` environment variable is set

### ❌ Authentication doesn't work
**Solution:** 
1. Check browser console for errors
2. Verify backend API is running
3. Test with the auth-debug.html tool

---

## Testing Your Deployment

1. **Register a new account**
   - Go to `/auth/register`
   - Use your LeetCode username
   - Create an account

2. **Test Dashboard**
   - Should show your LeetCode stats
   - Check if topics are loading

3. **Test Interview**
   - Go to `/dashboard/interview`
   - Should show a problem from your learning path

4. **Test Mentor**
   - Go to `/dashboard/mentor`
   - Try asking a coding question

---

## Need Help?

- **Vercel Docs:** https://vercel.com/docs
- **Check Logs:** Vercel Dashboard → Your Project → Deployments → View Logs
- **API Issues:** Check AWS CloudWatch logs for backend errors

---

## Repository Structure

```
Codeflowwithai/
├── frontend/              ← Deploy this folder
│   ├── app/              ← Next.js pages
│   ├── components/       ← React components
│   ├── lib/              ← API client & utilities
│   ├── public/           ← Static assets
│   ├── package.json      ← Dependencies
│   └── vercel.json       ← Vercel config
├── infrastructure/       ← AWS CDK (not deployed to Vercel)
└── lambda-functions/     ← Backend (not deployed to Vercel)
```

**Note:** Only the `frontend` folder is deployed to Vercel. The backend is already running on AWS.

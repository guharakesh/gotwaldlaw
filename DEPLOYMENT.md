# Gotwald Law Website - Deployment Guide

## Site is Ready! 🎉

The website has been built and is ready to deploy. Here's what was created:

### Features
- **Single-page responsive design** with smooth scrolling navigation
- **Forest green, gold, and cream** color scheme
- **All content sections:**
  - Hero with attorney photo and CTAs
  - Practice Areas (Criminal Defense, Family Law, Juvenile Law, Personal Injury)
  - About section with bio and credentials
  - Contact form with validation
  - Footer with legal disclaimer
- **Mobile responsive** with hamburger menu
- **Fast performance** (static site, minimal JavaScript)

## Local Development

```bash
# Start dev server
npm run dev

# Visit http://localhost:4321
```

## Deployment Options

### Option 1: Netlify (Recommended)

**Why Netlify:**
- Free hosting
- Automatic SSL
- Built-in form handling (contact form will work automatically!)
- Easy custom domain setup

**Steps:**

1. **Create GitHub repository** (if you haven't already)
   ```bash
   git init
   git add .
   git commit -m "Initial commit - Gotwald Law website"
   git remote add origin YOUR_GITHUB_REPO_URL
   git push -u origin main
   ```

2. **Deploy to Netlify:**
   - Go to [netlify.com](https://netlify.com)
   - Click "Add new site" → "Import an existing project"
   - Connect your GitHub account
   - Select your repository
   - Build settings (should auto-detect):
     - Build command: `npm run build`
     - Publish directory: `dist`
   - Click "Deploy site"

3. **Configure contact form:**
   - No additional setup needed! Netlify automatically detects the form
   - Form submissions will appear in Netlify dashboard under "Forms"
   - Set up email notifications in Netlify dashboard

4. **Add custom domain:**
   - In Netlify dashboard: Domain settings → Add custom domain
   - Enter `gotwaldlaw.com`
   - Follow DNS instructions (add CNAME or A record)
   - SSL certificate will be automatically configured

### Option 2: Vercel

**Steps:**

1. Install Vercel CLI
   ```bash
   npm i -g vercel
   ```

2. Deploy
   ```bash
   vercel
   ```

3. Follow prompts to connect to your Vercel account

4. Add custom domain in Vercel dashboard

**Note:** For contact form with Vercel, you'll need to:
- Add a serverless function for form handling, OR
- Use a service like Formspree or EmailJS

### Option 3: Other Static Hosts

The site is a static build (in the `dist/` folder), so you can deploy to:
- GitHub Pages
- Cloudflare Pages
- AWS S3 + CloudFront
- Any static hosting service

## Post-Deployment Checklist

- [ ] Test all navigation links
- [ ] Test contact form submission
- [ ] Verify on mobile devices
- [ ] Test phone number link (click-to-call)
- [ ] Test email link
- [ ] Verify images load correctly
- [ ] Check SSL certificate is active
- [ ] Test page speed (should be very fast!)

## Making Updates

To update content:

1. Edit the appropriate component file in `src/components/`
2. Run `npm run build`
3. Push changes to GitHub (Netlify/Vercel will auto-deploy)

Or edit directly in your repository and it will trigger a rebuild.

## Contact Form Setup (Netlify)

The form is already configured for Netlify Forms with:
- `data-netlify="true"` attribute
- Hidden `form-name` field
- All required fields

Netlify will:
- Automatically detect the form
- Store submissions in dashboard
- Send email notifications (configure in dashboard)

## Domain Configuration

For `gotwaldlaw.com`:

**If using Netlify:**
1. Add custom domain in Netlify
2. Update DNS records at your domain registrar:
   - Add CNAME record: `www` → `YOUR-SITE.netlify.app`
   - Add A record: `@` → Netlify's IP (provided in dashboard)

**If using Vercel:**
1. Add custom domain in Vercel dashboard
2. Update DNS records at your domain registrar per Vercel's instructions

## Need Help?

- [Astro Documentation](https://docs.astro.build)
- [Netlify Documentation](https://docs.netlify.com)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)

## Future Enhancements

Consider adding:
- Blog section for legal updates
- Client testimonials
- Google Analytics
- Live chat widget
- Appointment scheduling (Calendly integration)
- Spanish language version

# St Helens Remapping Website

Renko Remapping's St Helens location website - Professional ECU remapping and car tuning services.

**Live Site**: https://sthelens.renkoremapping.co.uk

## About

This is a location-specific website for Renko Remapping, targeting the St Helens area. Same professional service and Renko branding, optimized for the St Helens, Newton-le-Willows, and Prescot markets.

## Tech Stack

- React + TypeScript
- Vite
- Tailwind CSS
- React Router

## Local Development

**Prerequisites:** Node.js 16+

1. Install dependencies:
   ```bash
   npm install
   ```

2. Run the development server:
   ```bash
   npm run dev
   ```

3. Open http://localhost:5173

## Build

```bash
npm run build
```

The production build will be output to the `dist/` folder.

## Deployment

This site is configured for Netlify deployment:

1. Connect your GitHub repository to Netlify
2. Netlify will automatically detect the build settings from `netlify.toml`
3. The contact form will automatically work with Netlify Forms

### Netlify Configuration

- **Build Command**: `npm run build`
- **Publish Directory**: `dist`
- **Contact Form**: Automatically detected via Netlify Forms

## Contact Form Setup

The contact form uses Netlify Forms for submission handling. No backend required - form submissions will appear in your Netlify dashboard under Forms.

### How It Works

1. **Static Form in index.html**: The hidden form at the bottom of `index.html` is detected by Netlify's build bots during deployment
2. **React Form in Contact.tsx**: The visible form users interact with matches the static form's structure
3. **Form Detection**: Netlify automatically creates a form endpoint during the build process

### Troubleshooting: Form Not Detected

If Netlify doesn't detect your contact form, follow these steps:

1. **Check the Build Log**
   - Go to your Netlify site dashboard → Deploys → Click on the latest deploy
   - Look for "Forms detected" or "Forms not detected" in the build log
   - You should see: `Forms detected: contact`

2. **Verify Static Form in Built HTML**
   - After deploying, check the built `dist/index.html` file
   - Look for the hidden form near the bottom:
   ```html
   <form name="contact" method="POST" data-netlify="true" netlify-honeypot="bot-field" hidden>
     <input type="hidden" name="form-name" value="contact" />
     <input type="text" name="name" />
     <input type="email" name="email" />
     <input type="tel" name="phone" />
     <textarea name="message"></textarea>
   </form>
   ```

3. **Ensure Correct Form Attributes**
   - The form must have: `data-netlify="true"`
   - The form must have: `name="contact"`
   - Both the hidden static form AND the React form must have matching names

4. **Redeploy**
   - If form wasn't detected initially, trigger a new deploy:
   - Go to Deploys → Trigger deploy → Clear cache and deploy site
   - This forces Netlify to re-scan the HTML for forms

5. **Manual Form Creation (Last Resort)**
   - If automatic detection fails, manually create the form:
   - Go to Site settings → Forms → Add form manually
   - Name: `contact`
   - Fields: `name`, `email`, `phone`, `message`

### Testing the Form

After deployment:
1. Go to your live site: https://sthelens.renkoremapping.co.uk/contact
2. Fill out and submit the form
3. Check Netlify dashboard → Forms → Contact
4. You should see the submission appear

## SEO

- Location-optimized for St Helens
- Schema.org structured data
- Sitemap included
- Meta tags optimized for local search
- Geographic coordinates: 53.4500, -2.7374

## Repository

https://github.com/bluenose10/St-Helens

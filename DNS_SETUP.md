# DNS Configuration Guide for miloe.app

## Step 1: Domain Registration
1. Purchase the domain `miloe.app` from a domain registrar (e.g., Google Domains, Namecheap, etc.)
2. Ensure you have access to the domain's DNS settings

## Step 2: DNS Configuration
Add the following DNS records to your domain provider:

### A Records (for root domain)
```
@ 185.199.108.153
@ 185.199.109.153
@ 185.199.110.153
@ 185.199.111.153
```

### CNAME Record (for www subdomain)
```
www miloe.github.io.
```

### TXT Record (for GitHub Pages verification)
```
@ "github-pages-verification=YOUR_VERIFICATION_CODE"
```

## Step 3: GitHub Pages Configuration
1. Go to your GitHub repository settings
2. Under "Pages" section:
   - Set source to "main" branch
   - Enable "Enforce HTTPS"
   - Add custom domain: `miloe.app`

## Step 4: SSL Certificate
GitHub Pages will automatically provision an SSL certificate for your domain. This process may take up to 24 hours.

## Verification Steps
1. After DNS changes propagate (can take up to 48 hours):
   - Visit `https://miloe.app` to verify the site loads
   - Check that `https://www.miloe.app` redirects to `https://miloe.app`
   - Verify the SSL certificate is valid

## Troubleshooting
- Use `dig miloe.app` to verify DNS records
- Check GitHub Pages build status in repository settings
- Verify DNS propagation using online tools like [DNS Checker](https://dnschecker.org)

## Important Notes
- Keep your DNS records updated if GitHub Pages IP addresses change
- Maintain your domain registration to prevent expiration
- Regularly check SSL certificate status 
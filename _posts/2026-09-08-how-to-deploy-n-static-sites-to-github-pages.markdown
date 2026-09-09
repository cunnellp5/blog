---
layout: post
title:  "How to deploy multiple static sites to GitHub Pages"
date:   2026-09-08 20:33:10 -0600
categories: tech
toc: true
---

This post is a guide on hosting multiple subdomains, each backed by a dedicated GitHub repository, all running under a single custom domain.

> **Prerequisites**
* A custom domain already purchased and managed via a DNS provider (e.g., `philcunnell.dev`).
* A static site built using anything (Jekyll, React, Svelte, or plain HTML/CSS/JS) with an `index.html` entry point at the root.
{: .notice--info}

## Step 1: Configure Your DNS Records {#configure-dns}
1. Log into your domain registrar (such as GoDaddy, Cloudflare, etc.) and open the **DNS Management** section for your domain.
2. Add a new record to route traffic for your desired subdomain:
   * **Type:** `CNAME`
   * **Name:** `blog` (or whichever subdomain prefix you prefer)
   * **Value / Data:** `philcunnell.github.io` *(Note: Point this to your GitHub Pages user/organization profile domain rather than your root URL)* - my experimentation proves that this could also be `philcunnell.dev` - I dont really care about which one is right if they're both working

*This setup maps requests directly to `blog.philcunnell.dev`.*

## Step 2: Create the GitHub Repository {#create-github-repo}
1. Create a new repository on GitHub dedicated to this specific subdomain site.
2. Push your static site codebase to the repository, making sure your entry point (`index.html`) sits at the repository root.

## Step 3: Add the CNAME File {#add-CNAME}
At the root directory of your repository, create a plain-text file named **`CNAME`** (with no file extension). Inside the file, add your full custom subdomain on a single line:

```text
blog.philcunnell.dev
```

## Step 4: Configure GitHub Pages Deployment {#configure-gh-pages}
1. Navigate to your repository on GitHub and open **Settings > Pages**.
2. Under **Build and deployment**, set the source to **Deploy from branch**.
3. Select your target branch (e.g., `main`) and root folder (`/ (root)`), then click **Save**.
4. Look for the **Custom domain** input field, enter your full subdomain string (`blog.philcunnell.dev`), and click **Save**.

GitHub will automatically check your DNS provider for verification, issue an SSL/TLS certificate, and serve your static site live at the custom URL. 

*Repeat these steps to provision additional subdomains as needed.*
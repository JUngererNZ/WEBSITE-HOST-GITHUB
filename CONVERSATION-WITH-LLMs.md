https://medium.com/@vuusale/how-i-built-my-portfolio-website-for-almost-free-in-2-hours-ec9c7d1a3415



How I built my portfolio website for (almost) free in 2 hours
Vuusale
Vuusale

Follow
3 min read
·
Jan 7, 2026
55






Hi folks, in this blog, I’ll walk you through how I deployed my portfolio website within 2 hours for (almost) free. I had purchased a domain vusala.az for my portfolio website more than 1 year ago but kept procrastinating on it. One morning, I woke up, decided to close that mental tab in my mind, and soon realized that it was just a matter of a few hours of focused work.

## 1. Web Development
First, let’s start by building the website. Since it will contain no dynamic content, we will just need a static HTML page with some styling and some light animations.

In this phase, we will make use of ChatGPT, so don’t worry if you struggle with CSS styling like me. We will just explain to ChatGPT what kind of website we want and it will generate the code instantly, though it won’t be perfect every time.

I’m providing a sample prompt to write HTML, CSS, and JavaScript according to how you want it to look like:

Create a small, production-ready static portfolio (three files) for a personal [Put your field here] portfolio. Output must be three separate files exactly named and structured: index.html, style.css, and script.js. Do NOT use inline CSS/JS. Keep everything dependency-free (no frameworks, no external CSS libraries or JS libraries). Code should be clean, semantic, and commented where helpful. Design & tone: creative, modern, minimal, professional. [Add specific details according to preference, such as animation, sections, styling, color palette, fonts, etc.]

## 2. Hosting
We will use Github Pages to host our website for free.

Follow the steps below to upload your code to your Github account and activate Github pages.

Create a GitHub repository named <YOUR GITHUB USERNAME>.github.io (For a user/organization site, the repository name must match the GitHub username)
Add, commit and push your files to the repository. The folder structure should look like this:
index.html
style.css
script.js
Go to Settings → Pages.
Enable Github Pages from the main branch.

## 3. Deployment
You can stop here if you’re fine with using the default github.io domain.

To configure a custom domain for our website, we will purchase a domain from a registrar and then configure its DNS via Cloudflare.


### In the Cloudflare dashboard:

Add the new domain.
Keep the default settings, then select the Free plan.
Continue to activation and add the provided Cloudflare nameservers in your registrar’s dashboard as NS records.
Add 4 A records pointing to GitHub Pages IP addresses:
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
(Optional) add a CNAME record www pointing to your GitHub Pages domain (username.github.io).
Make sure Cloudflare proxy is disabled (keep DNS only).
In your Github repository:

Go to Settings → Pages.
In the Custom domain section, enter your domain. Don’t forget to check its status.
A commit will be created that adds a file named CNAME directly to the root of your source branch. Ensure this file exists and contains your custom domain (no extra spaces or newlines).
(Optional but recommended) check Enforce HTTPS (GitHub will issue a TLS certificate automatically).
Bonus: Set up a professional email
Enable email routing in Cloudflare.
Add your personal email address.
Add the DNS records provided by Cloudflare for routing.
Wait a few minutes for propagation.
Create a routing rule to forward emails sent to a custom email address to your personal mailbox.
Test by sending and receiving emails.
Now, you can add a professional email to your website and CV as contact information.

## Troubleshooting
Custom domain in Github pages is not active.
Add Github Pages A records to your domain in Cloudflare DNS settings.
github.io domain is active but my domain is not routing to it.
Check the CNAME file in the repository to ensure it does not contain any extra spaces or line breaks.
Conclusion
That’s it — now you have a clean portfolio website deployed in a couple of hours.

Sometimes all it takes is sitting down, doing the work, and realizing the task was never as big as it seemed.


https://dash.cloudflare.com/login


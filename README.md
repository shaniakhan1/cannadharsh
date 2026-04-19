# cannadharsh.com

Personal site for Dharsh Casinathen. Built as a single static `index.html` file. No build step, no dependencies.

## Deploying to GitHub Pages

1. Create a new public repository on GitHub. For a custom domain to work cleanly, any name is fine (e.g. `cannadharsh-site`).
2. Upload `index.html` (and this README) to the repo root.
3. Go to **Settings → Pages**.
4. Under **Source**, select `Deploy from a branch`, pick `main` and `/ (root)`, save.
5. Wait 1–2 minutes. Your site will be live at `https://<username>.github.io/<repo-name>/`.

## Pointing cannadharsh.com at GitHub Pages

Currently the domain is on Wix. To move it:

1. In GitHub → Settings → Pages, add `cannadharsh.com` as the custom domain. GitHub will create a `CNAME` file in the repo.
2. In your domain registrar (or Wix if the domain is registered through them, check **Wix → Domains**), update DNS:
   - Add 4 `A` records pointing `@` to:
     - `185.199.108.153`
     - `185.199.109.153`
     - `185.199.110.153`
     - `185.199.111.153`
   - Add a `CNAME` record for `www` pointing to `<username>.github.io`
3. Wait for DNS to propagate (usually under an hour, can take up to 24).
4. Back in GitHub Pages settings, enable **Enforce HTTPS**.
5. Once the new site is live and working, cancel the Wix plan.

**Heads up:** If the domain is registered *through* Wix, you may need to transfer it to a standard registrar (Namecheap, Cloudflare, Porkbun) first, or use Wix's DNS management to add the records. Wix makes this slightly annoying on purpose.

## Editing the site

Everything is in `index.html`. Content sections are clearly labeled with HTML comments (`<!-- ============ HERO ============ -->` etc). Colors, fonts, and spacing live in the `:root` CSS variables at the top of the `<style>` block.

To swap the portrait, replace the `src` on the `.hero-image-wrap img` with a new image URL (or add the image to the repo and reference it locally like `src="portrait.jpg"`).

## Contact form

There is no form, by design. The contact section is an email link going to `cannadharsh@gmail.com`. If a form is needed later, [Formspree](https://formspree.io) is the easiest drop-in (free tier covers 50 submissions/month).

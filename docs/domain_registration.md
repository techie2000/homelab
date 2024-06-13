# Domain name registration

In order to be able to access your homelab services externally via 'nice' recognisable url's like https://jellyfin.myhomelab.net you are going to need to own (or at the very least, have control of) your own domain name (https://myhomelab.net in this example).

:bulb: I would recommend purchasing your domain via [Cloudflare](cloudflare.com) as by doing so you don't have the extra effort of transferring the DNS registration to [Cloudflare](cloudflare.com) in order to continue with the rest of the homelab setup (like issuing Lets Encrypt certificates automatically).

:question: I already have a domain registered with another registration provider. What now?
  - You can transfer it to Cloudflare by following this guide https://developers.cloudflare.com/registrar/get-started/transfer-domain-to-cloudflare/

:warning: Pre-requisites for registering a new domain name with [cloudflare.com](cloudflare.com):
  - A registered user account at [cloudflare.com](cloudflare.com)

## Registering the new domain
  - The Cloudflare dashboard can be accessed at [dash.cloudflare.com](dash.cloudflare.com)
  - Go to `Domain Registration > Register Domains`
  - Search to see if the domain name you would like is free.
  - Follow the prompts to purchase/pay for the domain of your choice.

## Post domain registration actions
:bulb: Optional (but recommended):
  - Enable DNSSEC (Domain Name System Security Extensions)
    - GO to the Cloudflare dashboard [dash.cloudflare.com](dash.cloudflare.com)
    - Select `Domain Registration > Manage Domains`
    - Find the domain you where you want to activate DNSSEC and select Manage.
    - Select Configuration > Enable DNSSEC. If DNSSEC was previously activated, select Disable DNSSEC to disable it.
    - This is normally propogated quickly, but in a worst case, can tae up to 2 days. You can check on the status by going to `DNS > Settings` in the Cloudflare dashboard [dash.cloudflare.com](dash.cloudflare.com), and scroll down to DNSSEC.
  - WHOIS redaction
    - Follow Cloudflare's guide at https://developers.cloudflare.com/registrar/account-options/whois-redaction/
  - If you are part of the Apple (as oposed to Android) ecosystem, you can configure iCloud Custom Email Domains so that you can have me@myhomelab.net type email addresses.
    -  Follow Cloudflare's guide at https://developers.cloudflare.com/registrar/account-options/icloud-domains/

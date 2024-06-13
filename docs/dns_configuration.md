# DNS Configuration

Once you have your [domain registered](domain_registration.md) you can configure DNS entries so that Cloudflare can pass a url request like https://jellyfin.myhomelab.net to a service running on your homelab.

‼️ Exposing your homelab services in this way is risky - you are exposing your server to the internet hoards and the hackers who lurk there. You should not expose your local services to the internet without first taking precautions to protect yourself from inevitable attacks. This will be covered later but will consist of, amongst other things,
  - removing root password access
  - configuring the use of public/private keys for passwordless log in
  - only allowing local ip's to access ssh (maybe even just specific terminals)

## Configuring Cloudflare DNS
  - The Cloudflare dashboard can be accessed at [dash.cloudflare.com](dash.cloudflare.com)
  - Go to `DNS > Records`
  - Configure an `A record` for your `myhomelab.net` domain that points to the external IP address of your gateway (i.e. the IP assigned by your ISP).
    - ⚠️ This assumes that you have a fixed IP address. If you don't have a fixed IP address, you will need to take additional steps to get your current/changing IP address updated for this record. Notes will be added later on how to do this, but it will either require you to make use of an inbuilt feature on your router, or the use of a third-party program that makes use of the Cloudflare api to update the record when it detects your IP has changed.

💡 Until you have taken the security precautions to protect yourself from external attack, you can optionally configure Cloudflare DNS records that point to your services local network addresses. This means that at home, you can still use FQDN to access your local services rather than usings IP addresses or setting them in a local DNS server or hosts file(s). Then, when you have completed the secure setup and are ready to have the servces made accesible from outside of your local netowrk, you simply delete these reords at Cloudflare.
  - Configure an `A record` for say `apache.myhomelab.net` and point it to the local (fixed) IP address you have it running on, e.g. 10.192.168.45. Now, when you access https://apache.myhomelab.net whilst inside your home network, you will access your webserver. If you are sitting outsie of your home network, then the site will be inaccessible.

When you have taken the security precautions to protect yourself from external attack, you can configure them to be accesible via FQDN:
  - Congfigure a `cname record` for `*` that points to `myhomelab.net`. This will direct requests to say https://myservice.myhomelab.net or https://a.n.other.service.myhomelab.net to the same IP address you congigurred in the `A record` step above.
    - This means you can add as many services as you like without the need to set them up individulally in Cloudfalre's DNS.
    - 💡 optionally you can choose to proxy this record through Cloudflare to speed up delivery content. This is is useful if you are hosting say a website on your homelab that you are exposing publicly.
      - ℹ️ Cloudflare's T&C's forbid you from proxying streaming media (on the free plan at least). If you have some services that would break this rule, you can add another `cname record` for say `*.ncfp` (short for 'no cloudflare proxy') that also points to `myhomelab.net` and ensure you do NOT turn on the flag to proxy this record. Doing this, you can have say https://streamingservice.ncfp.myhomelab.net which will still route to your homelab but will not proxy what is served from it and thus comply with Cloudflare's T&C's.
    - Remove any `A record` DNS entries that you optionally setup above - else when you access the FQDN fromoutsie your local netowrk, you will still not be able to access the service.

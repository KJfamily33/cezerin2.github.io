## 7. Setup domain with CloudFlare
[Cloudflare.](https://www.cloudflare.com)

 - Get droplet IP on DigitalOcean
![DigitalOcean IP Address](./images/do-ip.png)

 - Add `A` and `CNAME` to DNS on CloudFlare
![CloudFlare DNS](./images/cf-dns.png)
 - Set SSL to `Flexible` on CloudFlare
![CloudFlare SSL](./images/cf-ssl.png)

 - Turn on `Always use HTTPS` on CloudFlare
![CloudFlare Always HTTPS](./images/cf-alway-https.png)

 - Add `A` record for admin dashboard:
 
 Type: A
 Name: admin
 Content: your-droplet-ip-address

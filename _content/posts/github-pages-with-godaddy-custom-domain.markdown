
{
"title": "GitHub pages with GoDaddy custom domain",
"description": "How to configure your GitHub website using GoDaddy custom domain",
"created": "2014-06-21T12:04:11Z",
"tags": ["static blog generator", "GoDaddy"],
"slug": "github-pages-with-godaddy-custom-domain"
}


When I was setting up this blog using [Dnevnik](https://github.com/cyberdot/dnevnik) static site generator
on GitHub Pages, I wanted to configure it to use my [cyberdot.co.uk](http://cyberdot.co.uk) domain name.
 
My domain registrar is GoDaddy.

It turned out to be quite easy to do and here are the steps:

1. Create a file named CNAME (it has to be in upper case) and save it in your generated web log root directory.

   [![CNAME file](/assets/img/posts/cname_src.png "CNAME file")](/assets/img/posts/cname_src.png "CNAME file")

2. Open CNAME file with your favourite text editor and type in your domain name (in my case it was [cyberdot.co.uk](http://cyberdot.co.uk) )

3. Don't forget to commit your file to git and then deploy your generated blog to GitHub.

4. Log in to your GoDaddy account, open "Domain details" page and click on "DNS Zone file" tab for your domain
  [![GoDaddy domain details](/assets/img/posts/godaddy_domain_details.png "GoDaddy domain details")](/assets/img/posts/godaddy_domain_details.png "GoDaddy domain details")

5. Update A record IP address value to: **192.30.252.153**
  [![A record IP](/assets/img/posts/a_host_update.png "A record IP")](/assets/img/posts/a_host_update.png "A record IP")

6. Also update www ALIAS records to your username.github.io account
  [![www ALIAS update](/assets/img/posts/www_update.png "www ALIAS update")](/assets/img/posts/www_update.png "www ALIAS update")

7. Give it some time and lo and behold, you've got GitHub pages working with your GoDaddy custom domain.




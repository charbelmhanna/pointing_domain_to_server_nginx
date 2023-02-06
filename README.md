# pointing_domain_to_server_nginx


When you point your domain to the server, you need to follow those steps in order to point it. 



1. cd /etc/nginx/sites-available


2. touch domainname.com

3. nano domainname.com

4. if vuejs add this 
```
server {
    listen  80;
    listen [::]:80;
    server_name domainanme.com;
    root /home/domainname.com; #where did you add the folder project 
    charset utf-8;

    index   index.html index.htm;
    # Always serve index.html for any request
    location / {
        root {{app_root}}/dist;
        try_files $uri /index.html;
    }
    error_log  /var/log/nginx/vue-app-error.log;
    access_log /var/log/nginx/vue-app-access.log;
}
```
5.save 

6. create a simlink 

7. sudo ln -s domainname.com ../sites-enabled/domainname.com

8. done

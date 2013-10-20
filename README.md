dokku-dokkuapp
==============

dokku-dokkuapp is a plugin for [dokku][1] that automatically creates a 
random `[appname].dokkuapp.com` subdomain for newly deployed applications. 
This enables apps to quickly obtain a url without needing to register
a domain name and configure DNS settings.

This plugin calls the [dokkuapp.com api][2] to create a DNS entry that
assigns a subdomain to the deploy server's IP address.

[1]: https://github.com/progrium/dokku
[2]: https://github.com/mikexstudios/dokkuapp.com#readme

Installation and Usage
----------------------

1. Install the plugin by cloning into the dokku plugins directory:
    ```sh
    git clone https://github.com/mikexstudios/dokku-dokkuapp.git /var/lib/dokku/plugins/dokku-dokkuapp
    ```
2. Make sure that your app (hosted in `/home/git/`) does *not* contain 
   a `VHOST` file. For new application, no `VHOST` file should exist.
   But if you have a `VHOST` file in your `/home/git/[myapp]/` directory,
   delete it.

3. Re-push your application to your dokku server. At the end of your 
   deploy, you should see:
    ```
    =====> Application deployed:
           http://[myapp].dokkuapp.com
    ```

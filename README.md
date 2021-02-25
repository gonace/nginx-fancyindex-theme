# Modern theme for nginx's fancyindex module
> This theme is heavily influenced by [nginx-fancyindex-flat-theme](https://github.com/alehaa/nginx-fancyindex-flat-theme) and uses files from this repository.

[![](https://img.shields.io/github/issues-raw/gonace/nginx-fancyindex-modern-theme.svg?style=flat-square)](https://github.com/gonace/nginx-fancyindex-modern-theme/issues)

![](readme/screenshot.png)


## About
The [fancyindex module](https://github.com/aperezdc/ngx-fancyindex) of
[nginx](http://nginx.org/) has the powerful capability to be customizable.
Instead of using an external application, this gives us the ability to use just the webservers' capabilities to generate beautiful directory listings.

This theme provides a simple, flat interface based on
[Bootstrap 5](https://getbootstrap.com), [Font Awesome](https://fontawesome.com)
and (for easy navigation in galleries). In combination with
the browser's preview capability, accessing the majority of files should be
possible, giving the user easy access without a single line of server-side
dynamic code.


## Usage
1. Get the latest ressources from [GitHub releases](https://github.com/gonace/nginx-fancyindex-modern-theme/releases)
   or build them on your own by running `make` inside this repository and copy
   these files into any location accessible by *nginx*.
2. Configure your vhost to use the theme's ressources for fancyindex:
    ```
    # Fancyindex
    fancyindex             on;
    fancyindex_header      "/theme/header.html";
    fancyindex_footer      "/theme/footer.html";
    fancyindex_show_path   off;
    fancyindex_name_length 255;
    fancyindex_exact_size  off;
    fancyindex_localtime   on;
    fancyindex_time_format "%Y-%m-%d %H:%M:%S";

    location /theme {
        alias /usr/share/nginx/themes/modern;
    }
    ```
    > We recommend taking a look at [fancyindex_time_format](https://github.com/aperezdc/ngx-fancyindex#fancyindex_time_format) to customize the date-time formats.

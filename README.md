# Redirecting HTTP pages to HTTPS

The purpose of this tutorial is to assist in the creation of web page redirection with **HTTP** `HyperText Transfer Protocol` to **HTTPS** `Hyper Text Transfer Protocol Secure`. There are several ways to do this, however, we'll cover only one of them in this tutorial. The `.htaccess` file will be used. = ]

> This tutorial does not explain the installation and/or purchase of SSL security certificate. Another very important detail is that you need to get in touch with your hosting provider and identify if the procedure covered in this tutorial is allowed in your contracted plan.

## Requirements

Hosting with `SSL` security certificate installed.

## Files

You can use the files available in this tutorial or create them on your own. 

- The [ .htaccess ]( .htaccess ) file must be created in the root folder of the site, usually named `public`; 

- The folder [ test ]( test/ ) and the file [ test.html ]( test/test.html ) are optional and must also be created in the root folder of the site.

## Development

Assuming your hosting is already configured by enabling the HTTPS protocol, perform the following procedures:

Summary

- New file;
- Folder and test file;
- Send to the lodging.

**New file**

Create a new file named `.htaccess` and enter the following data:

<pre>
  RewriteEngine On
  RewriteCond %{HTTP:X-Forwarded-Proto} !https
  RewriteCond %{HTTP_HOST} ^www.mydomain.com [NC]
  RewriteRule ^(.*)$ https://www.mydomain.com/$1 [L,R=301]
</pre>

> If your site already exists this file just add the above code. Do not forget to change `mydomain.com` to the correct one. \o/

**Folder and test file**

To identify if the `.htaccess` file is working, we will use a folder and a file as an example. *( This procedure is optional )*

Create a folder named [ test ]( test/ ) and inside this folder create a file named [ test.html ]( test/test.html ) with the following data:

**Send to the lodging**

After performing the above procedures, send the folder and files to your hosting. Use your favorite FTP program to do this.

The structure of the folder and the files will look similar to the chart below:

<pre>
├── test
│   └── test.html
├── .htaccess
</pre>

> Graphic example inspired by: https://github.com/willianjusten/braziljs-16

## Test

After performing all the previous procedures, access the links below:

> www.yourdomain.com and also www.yourdomain.com/test/test.html

When loading the 2 pages, check if something similar appears with:

> https://www.yourdomain.com and also https://www.yourdomain.com/test/test.html 

If the address bar displays a `lock` and the domain starts with `https://` everything has occurred as expected. If this does not happen, I advise you to contact your hosting to see if this is allowed and if it was done correctly.

## Use

I am currently using this type of redirection in the hosting in which my site, and others managed by me, are stored. **I do not want to promote or denigrate the image of any hosting provider**. This tutorial has a single purpose that is to share something that helped a lot when I had to do this procedure.

> It is always good to remember that this procedure should be performed with the guidance of your hosting!

## Credits

I leave here the credits for [ Hostnet ]( https://www.hostnet.com.br/ ) about the file [ .htaccess ]( .htaccess ).

## Author

**[ APSantos-Pires ]( https://github.com/APSantos-Pires )** - *Initial model*

## Contribution

Contribute to make this **Redirecting HTTP pages to HTTPS** model better. \o/

1. *Fork!*
2. Create your *feature branch*: `git checkout -b myNewFeature`
3. Confirm the changes: `git commit -am 'Add some comment'`
4. Send your *branch*: `git push origin myNewFeature`
5. Send a request for *pull request*.

= ]

## Version

> Release: 1.0.1

## License

This **Redirecting HTTP pages to HTTPS** template is licensed under the MIT License - see the file [ LICENSE ]( LICENSE ) for details.

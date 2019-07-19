---
title: How to create an https server?
date: '2011-08-26T10:08:50.000Z'
tags:
  - https
difficulty: 1
layout: knowledge-post.hbs
---

*If you're using [Nodejitsu](http://nodejitsu.com)*, we handle HTTPS for you. Free SSL on jit.su and nodejitsu.com subdomains, and SSL on custom domains for business customers.
*It's never necessary to create an HTTPS server yourself.*

- - -

To create an HTTPS server, you need two things: an SSL certificate, and Node's built-in `https` module.

We need to start out with a word about SSL certificates.  Speaking generally, there are two kinds of certificates: those signed by a 'Certificate Authority', or CA, and 'self-signed certificates'.  A Certificate Authority is a trusted source for an SSL certificate, and using a certificate from a CA allows your users to be trust the identity of your website. In most cases, you would want to use a CA-signed certificate in a production environment - for testing purposes, however, a self-signed certicate will do just fine.

To generate a self-signed certificate, run the following in your shell:

    openssl genrsa -out key.pem
    openssl req -new -key key.pem -out csr.pem
    openssl x509 -req -days 9999 -in csr.pem -signkey key.pem -out cert.pem
    rm csr.pem

This should leave you with two files, `cert.pem` (the certificate) and `key.pem` (the private key). This is all you need for a SSL connection. So now you set up a quick hello world example (the biggest difference between https and [http](/how-do-i-create-a-http-server) is the `options` parameter):

    var https = require('https');
    var fs = require('fs');

    var options = {
      key: fs.readFileSync('key.pem'),
      cert: fs.readFileSync('cert.pem')
    };

    var a = https.createServer(options, function (req, res) {
      res.writeHead(200);
      res.end("hello world\n");
    }).listen(8000);

NODE PRO TIP: Note `fs.readFileSync` - unlike `fs.readFile`, `fs.readFileSync` will block the entire process until it completes.  In situations like this - loading vital configuration data - the `sync` functions are okay.  In a busy server, however, using a synchronous function during a request will force the server to deal with the requests one by one!

Now that your server is set up and started, you should be able to get the file with curl:

    curl -k https://localhost:8000

or in your browser, by going to https://localhost:8000 . 

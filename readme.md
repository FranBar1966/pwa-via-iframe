Convert Web to APP/PWA
======================
Convert Web sites into Progressive Web Applications using IFRAME.

![Progressive_Web_App](https://user-images.githubusercontent.com/114579121/207160550-9564627e-3ce1-4984-8a53-13906561c3b1.png)

It works with any Web site that allows it to be displayed inside an iframe. Large sites like google, facebook, etc. do not allow this.

## Demo

As an example I have created a PWA from this same repository that you can see in /example-ipwa/

For this repository to be installed as PWA in mobile devices as well as in Windows/iOS/Linux desktop go to: [example PWA via iframe](https://thenocoder.github.io/pwa-via-iframe/example-ipwa/)

## Get started

Simply download this repository and copy the /ipwa/ directory to the site you want to convert to PWA.

The /example-ipwa/ directory can be ignored or deleted.

You will need to edit the /ipwa/index.html file and in the IFRAME SRC you put the URL of the site you want to convert.

It is not necessary that the code of this repository is in the same domain as the site to convert, for example, you can install this repository on your localhost, change the iframe to htttps://example.com to convert example.com into PWA by accessing http://localhost/ipwa/

You could even install on localhost (or on any domain) numerous PWAs by simply adding more directories with different names http://localhost/ipwa-1/ http://localhost/ipwa-2/ ...

Note that while on http://localhost you don't need HTTPS to make it work as a PWA, on any domain on the Internet, it won't work without an SSL or HTTPS certificate.

## Changes you will need to make

As explained above, the only mandatory change is to the /ipwa/index.html file.

```hmtl
 <iframe src="https://thenocoder.github.io/" ... </iframe>
```

Change to:
```hmtl
 <iframe src="https://site-to-be-converted-to-pwa..." ... </iframe>
```

### Change PWA name and description

To change the name of the PWA you need to modify two files, /ipwa/index.html and /ipwa/manifest.json

In /ipwa/index.html change "Iframe PWA" to the name of your PWA:
```hmtl
<meta name="application-name" content="Iframe PWA">
<meta name="apple-mobile-web-app-title" content="Iframe PWA">
```

In /ipwa/manifest.json change "short_name", "name" and "description":
```hmtl
"short_name": "Iframe PWA",
"name": "My IFrame Progressive Web App",
"description": "My Progressive Web App via iframe",
```

In /ipwa/manifest.json you can also change the background and theme color:
```hmtl
"background_color": "#FFFFFF",
"theme_color": "#000000",
```

### Change icons

You can change the PWA icons to your own, simply in the /ipwa/icons/ directory overwrite them, they must be PNG and the size is specified in the filename.

### Change ipwa directory

In case you simply want to rename /ipwa/ or add more /ipwa-1/, /ipwa-2/ ... You will have to change all files in this repository /ipwa/ to the name you want.

In /ipwa/index.html
```hmtl
...
<link rel="manifest" href="/ipwa/manifest.json">
...
<script>
    ...
    serviceWorkerReg = navigator.serviceWorker.register('/ipwa/service-worker.js');
    ...
</script>
```

In /ipwa/manifest.json
```hmtl
...
"id": "/ipwa/",
"start_url": "/ipwa/",
"icons": [
    {
        "src": "/ipwa/icons/32x32.png",
        ...
    },
    {
        "src": "/ipwa/icons/192x192.png",
        ...
    },
    {
        "src": "/ipwa/icons/512x512.png",
        ...
    },
    {
        "src": "/ipwa/icons/512-maskable.png",
        ..
    }
]
```

## License

MIT License

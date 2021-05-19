+++
title = "Setup"
date = 2021-05-18T15:58:47+02:00
weight = 4
chapter = false
+++

1. Create basic HTML & CSS for the future WPA :
    a. `index.html`
    
    ```html
    <!doctype html>
    <html lang="en">

    <head>
        <meta charset="utf-8">
        <title>Hello World</title>
        <link rel="stylesheet" href="css/style.css">

        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta name="theme-color" content="white"/>
    </head>

    <body class="fullscreen">
        <div class="container">
            <h1 class="title">Hello World!</h1>
        </div>
    </body>

    </html>
    ```

    b. `css/style.css`
    
    ```css
    body {
        font-family: sans-serif;
    }
    
    /* Make content area fill the entire browser window */
    html,
    .fullscreen {
        display: flex;
        height: 100%;
        margin: 0;
        padding: 0;
        width: 100%;
    }
    
    /* Center the content in the browser window */
    .container {
        margin: auto;
        text-align: center;
    }
    
    .title {
        font-size: 3rem;
    }
    ```

2. Serve in a webserver (apache, nginx...) as HTTPS (valid certificate) -> [Tuto create valid https local](https://gist.github.com/cecilemuller/9492b848eb8fe46d462abeb26656c4f8).

3. `manifest.json`

    a. Create `manifest.json` :

    ```json
    {
        "name": "Hello World",
        "short_name": "Hello",

        "lang": "en-US",
        "start_url": "./index.html",
        "display": "standalone",

        "theme_color": "#ffffff",
        "background_color": "#ffffff" 
    }
    ```

    b. Import `manifest.json` in `index.html` :

    ```html
        <link rel="manifest" href="./manifest.json">
    </head>
    ```

4. [Generate icons with https://realfavicongenerator.net/](https://realfavicongenerator.net/) :
     
    a. Copy all link and meta (**except manifest**) in HEAD of `index.html`

    b. Extract downloaded package in /images.
     
    c. copy `icons` key from `/images/site.webmanifest.json` to `manifest.json`.

    d.  Adapt icons url if necessary.

    e. delete `/images/site.webmanifest.json`.

5.  Service Worker :

    a. Install Google workbox CLI :
    ```shell
    npm install workbox-cli --global 
    ```

    b. Run workbox wizard (will create config file `../workbox-config.js`) : 
    ```shell
    cd ..
    workbox wizard
    ```

    c. Generate Service Worker (sw.js) from config file : 
    ```shell
    workbox generateSW workbox-config.js
    ```

    d. Create `js/main.js` to load Service Worker (sw.js) :
    ```js
    window.onload = () => {
        'use strict';

        if ('serviceWorker' in navigator) {
            navigator.serviceWorker
                .register('./sw.js');
        }
    }
    ```

    e. Import `js/main.js` in `index.html` :
    ```html
        <script src="js/main.js"></script>
    </body>
    ```
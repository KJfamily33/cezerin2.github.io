## FAQ

Feel free to add your FAQs.
You can add it by making Pull Request to the https://github.com/Cezerin2/cezerin2.github.io

### CORS (Allow-Cross-Origin) Error. How to fix?!

You need to change all configs and replace all localhost with your ip number or domain name.

How it's work.

Check file: /cezerin2/src/index.js
This code:

```javascript
// CORS headers
    var allowedOrigins = security.getAccessControlAllowOrigin();
    var origin = req.headers.origin;
    if (allowedOrigins === '*') {
        res.setHeader('Access-Control-Allow-Origin', allowedOrigins);
    } else {
        if (allowedOrigins.indexOf(origin) > -1) {
            res.setHeader('Access-Control-Allow-Origin', origin);
        }
    }
```    
And this file: /cezerin2/src/lib/security.js

```javascript
const getAccessControlAllowOrigin = () => {
    return [settings.storeBaseUrl, settings.adminBaseURL] || '*';
};
```

storeBaseUrl and adminBaseURL settings located in your config /cezerin2/config/server.js
  
  
### Question 1

Answer 1

[**GitHub Issues**](https://github.com/cezerin2/cezerin2/issues): https://github.com/cezerin2/cezerin2/issues

Beneffis
1. Fast load
2. Offline support

 - `push` events is when the backend send events to the browser

```javascript
navigator.serviceWorker
    .register(swURL, {
        scope: '/app' // With path service worker will intercept request, default is root
    })
    .then(registration =>
        console.log('SW registered onver scope', registration.scope)
    );
```

## In Chrome DevTools
 - `Update on reload` in devTools/Application will upload service worker once page is reload
 - `Bypass for network` in DevTools will force load content from network


All cache is stored in `Cache Storage`
Service Worker can on handle request from same level or bellow it is served

## Tips

 - It's good to use `networkFirst()` cache strategy from API calls

## Examples

### Making some actions before install ..

```javascript
self.addEventListener('install', event => {
  const asyncInstall = new Promise(resolve => {
    console.log("Waiting to resolve...")
    setTimeout(resolve, 5000)
  })

  event.waitUntil(asyncInstall) // Wait to install
})
```

### Caching others routers like CDN Contents

Cache all `*.min` for `css` or `js` files with `staleWhileRevalidate` strategy cache

> staleWhileRevalidate will server fast as possible from cache and updating the cache in background

```javascript
workbox.routing.registerRoute(
  new RegExp('https:.*min\.(css|js)'),
  workbox.strategies.staleWhileRevalidate({
      cacheName: 'cdn-cache' // Will use thes name on CacheStorage
  })
)
```

### Listening for ServiceWorker updates

```javascript
navigator.serviceWorker.register('./sw.js').then(reg => {
    reg.onupdatefound = () => { // Once new update found for this ssw
        sw.onstatechange = () => {
            if(sw.state === 'installed') {
                if (navigator.serviceWorker.controller) {
                    // 'A new version available'
                } else {
                    // 'Contents are now offline '
                }
            }
        }
     } 
})
```

### Handle requests

This will return error if you are offline

```javascript
self.addEventListener('fetch', event => {
  if(event.request.method === "POST" || event.request.method === "DELETE") {
    event.respondWith(
      fetch(event.request).catch(err => {
        return new Response(
          JSON.stringify({ error: "This action disabled while app is offline" }), {
            headers: { 'Content-Type': 'application/json' }
          }
        )
      })
    )
  }
})
```

# <link rel=preconnect> and <link rel=dns-prefetch>

Every resource on network should walk through the journey of lookup the domain, resolve IP, setup an connection and encrypt the connection. This journey is called [Round Trip Time (RTT)][2]

## Establish early connections with rel=preconnect 

Adding rel=preconnect to a <link> infor browser to establish a connection with the domain

[![pre-connect][3]][1]


## Resolve domain name early with rel=dns-prefetch

Tell the browser to resolve DNS early

```
<link rel="dns-prefetch" href="http://example.com">
```

YOu can use `dns-prefetch` as fallkback from `preconnect`

```
<link rel="preconnect" href="http://example.com">
<link rel="dns-prefetch" href="http://example.com">
```

[1]: https://web.dev/preconnect-and-dns-prefetch/
[2]: https://developer.mozilla.org/en-US/docs/Glossary/Round_Trip_Time_(RTT)
[3]: preconnect.png

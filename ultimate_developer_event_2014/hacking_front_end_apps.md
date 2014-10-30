## Hacking front-end apps

### Alex Sexton

__Summary:__
Writing web applications is fun. Getting hacked is not fun. This talk will walk through several different ways that websites, especially front-end heavy ones, are being hacked. It will cover cross site scripting, and resource forgery as well as introduce some new protective measures for writing secure web apps.

---

* Mike West - https://mikewest.org/2013/09/frontend-security-frontendconf-2013
* Mike Taylor - http://www.youtube.com/watch?v=zg1lVCwqtw8

web security is __hard__: "All you have to do is never make a single mistake."

web developers, not security researchers, are the core audience of internet security.

"I discount the probability of perfection" -> "We all have deadlines"

### Use HTTPS/SSL

now have free options:

	* https://www.cloudflare.com/ssl

#### Content injection - XSS

``` js
<script>alert('hacked');</script>
```

You cannot detect malicious code

#### CSS Hacks

visited link hack

timing attacks (security by inaccuracy)
	
* 16ms to render regular link; >60ms to render link with drop shadow

#### JSON-P

use CORS

#### cross-site resource forgery

solution is CSRF tokens

see contextis white paper

#### Content Security Policy

https://developer.mozilla.org/en-US/docs/Web/Security/CSP/Introducing_Content_Security_Policy

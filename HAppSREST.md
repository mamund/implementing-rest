# Introduction #

This is a stub article for REST in [HAppS](http://happs.org/), a web framework for Haskell.

_From the [HAppS site](http://happs.org/):_

> Write web services really easy using an elegant monadic framework for managing control-flow within your server. Use the built-in proxy functionality so your ajax apps can easily access the data they need anywhere on the internet. Take advantage of long transactions and lightweight threads for comet apps that need to handle tens of thousands of concurrent users on a single box and it can be as simple as:
```
import HAppS.Server 
main = simpleHTTP nullConf [ method GET $ ok "Hello World" ] 
```
# tokio-socks5

An implementation of a SOCKSv5 proxy server built on top of `tokio-core`.

[![Build Status](https://travis-ci.org/tokio-rs/tokio-socks5.svg?branch=master)](https://travis-ci.org/tokio-rs/tokio-socks5)
[![Build status](https://ci.appveyor.com/api/projects/status/lqqm4htaqfp5uf43?svg=true)](https://ci.appveyor.com/project/alexcrichton/tokio-socks5)

## Usage

First, run the server

```
$ cargo run
   ...
Listening for socks5 proxy connections on 127.0.0.1:8080
```

Then in a separate window you can test out the proxy:

```
$ export https_proxy=socks5h://localhost:8080
$ curl -v https://www.google.com
```

# License

`tokio-socks5` is primarily distributed under the terms of both the MIT
license and the Apache License (Version 2.0), with portions covered by various
BSD-like licenses.

See LICENSE-APACHE, and LICENSE-MIT for details.

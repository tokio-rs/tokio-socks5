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

If you have an older version of libcurl which doesn't support the `socks5h` scheme,
you can try:

```
$ curl -v --socks5-hostname localhost:8080 https://www.google.com
```

The server is hardcoded to use Google's public DNS resolver (IPv4 address 8.8.8.8).
If you can't use external DNS services, change the address in the source and
rebuild the server.

# License

This project is licensed under either of

 * Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or
   http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license ([LICENSE-MIT](LICENSE-MIT) or
   http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in Serde by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.

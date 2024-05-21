# SHA

RFC 6234: US Secure Hash Algorithms (SHA and SHA-based HMAC and HKDF).

## Version

The source code (*seems to be*) from <https://www.rfc-editor.org/rfc/rfc6234#section-8>. There is no version, so the publication date (*May 2011*) is used to form the version `2011.5.1`.

## License

The license seems to be [this](https://trustee.ietf.org/documents/trust-legal-provisions/) (*the `copyright` file*). It is not really an "Open Source", but seems to be "safe" enough. Apparently, it does not allow modifications. There is also some FAQ [here](https://trustee.ietf.org/about/faq/).

## Building

It is meant to be built with vcpkg using [this port](https://github.com/retifrav/vcpkg-registry/tree/master/ports/sha). Alternatively, you can copy the following files manually:

- [CMakeLists.txt](https://github.com/retifrav/vcpkg-registry/blob/master/ports/sha/CMakeLists.txt)
- [Config.cmake.in](https://github.com/retifrav/vcpkg-registry/blob/master/ports/decovar-vcpkg-cmake/common/Config.cmake.in)
- [Installing.cmake](https://github.com/retifrav/vcpkg-registry/blob/master/ports/decovar-vcpkg-cmake/common/Installing.cmake)

and then build the project as usual:

``` sh
$ cd /path/to/rfc6234-sha
$ mkdir build && cd $_
$ cmake -G Ninja -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX="../install" ..
$ cmake --build . --target install
```

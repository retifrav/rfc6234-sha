# SHA

RFC 6234: US Secure Hash Algorithms (SHA and SHA-based HMAC and HKDF).

## Version

The source code (*seems to be*) from <https://rfc-editor.org/rfc/rfc6234#section-8>. There is no version, so the publication date (*May 2011*) is used to form the version `2011.5.1`.

## License

The code here is the reference implementation from [RFC 6234, Section 8](https://rfc-editor.org/rfc/rfc6234#section-8), which makes it a *Code Component* of that RFC. Under [Section 4.e](https://trustee.ietf.org/documents/trust-legal-provisions/) of the IETF Trust Legal Provisions, Code Components are licensed under the three-clause Revised BSD License, which is reproduced in [`LICENSE`](./LICENSE) and is also carried in the header of `include/sha.h`. The SPDX identifier is `BSD-3-Clause`.

Two things are worth mentioning in addition to that:

1. RFC 6234 calls this the *"Simplified BSD License"*, which is the conventional name for the two-clause BSD license. That name was an error in the TLP itself, and the IETF Trust [corrected it](https://trustee.ietf.org/documents/trust-legal-provisions/) on 21 September 2021 - the text it provides was always the Revised (*three-clause*) BSD License. Many RFCs copied the wrong name;
2. The TLP does restrict modifying and redistributing the text of an RFC *document*. That restriction does not extend to Code Components extracted from it, so this code is ordinary open source and may be modified and redistributed under the BSD terms above.

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

# [Blockchain Commons Crypto Base](https://github.com/BlockchainCommons/bc-crypto-base)

**Well-Reviewed and Audited Cryptographic Functions for Use in [Blockchain Commons](https://www.BlockchainCommons.com)  Software Projects**

These are selected cryptographic functions used by various [Blockchain Commons](https://www.BlockchainCommons.com) software projects that have have been vetted by the developers as having been sufficiently well-reviewed and/or cryptographically audited by other parties, but also meet our specific needs (for instance to be able to run on embedded hardware).

## Installation

```bash
$ ./configure
$ make check
$ sudo make install
```

This sequence runs the module's unit tests.

## Use

1. Link against `libbc-crypto-base.a`.
2. Include the umbrella header in your code:

```c
#include <bc-crypto-base/bc-crypto-base.h>
```

## Notes for Maintainers

Before accepting a PR that can affect build or unit tests, make sure the following sequence of commands succeeds:

```bash
$ ./configure
$ make distcheck
$ make distclean
```

`make distcheck` builds a distribution tarball, unpacks it, then configures, builds, and runs unit tests from it, then performs an install and uninstall from a non-system directory and makes sure the uninstall leaves it clean. `make distclean` removes all known byproduct files, and unless you've added files of your own, should leave the directory in a state that could be tarballed for distribution. After a `make distclean` you'll have to run `./configure` again.

## Origin, Authors, Copyright & Licenses

Unless otherwise noted (either in this [/README.md](./README.md) or in the file's header comments) the contents of this repository are Copyright © 2020 by Blockchain Commons, LLC, and are [licensed](./LICENSE) under the [spdx:BSD-2-Clause Plus Patent License](https://spdx.org/licenses/BSD-2-Clause-Patent.html).

The table below establishes provenance (repository of origin, permalink, and commit id) for each source file in this repository. Contributors to these files are listed in the commit history for each file, first in this repo, then in the repo of their origin.

In most cases, the authors, copyright, and license for each file reside in comments in the source. When it does not we have attempted to attribute it accurately below.

| File      | From                                                         | Commit                                                       | Authors & Copyright (c)                                | License                                                     |
| --------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------ | ----------------------------------------------------------- |
| bc-crypto-hash.h | [blockchaincommons/bc-crypto-base](?) | [?](?) | 2020 Blockchain Commons, LLC  | [BSD-2-Clause-Patent](https://spdx.org/licenses/BSD-2-Clause-Patent.html)                        |
| hmac.c    | [trezor/trezor-firmware](https://github.com/trezor/trezor-firmware/blob/49fe64f84c5fc17f5680daaf03b124a2b8f26c3b/crypto/hmac.c) | [fdad317](https://github.com/trezor/trezor-firmware/commit/fdad317d8c5d11bc4734f8cf07b1d589fb475209) | 2013-2014 Tomas Dzetkulic<br />2013-2014 Pavol Rusnak  | [MIT](https://spdx.org/licenses/MIT)                        |
| hmac.h    | [trezor/trezor-firmware](https://github.com/trezor/trezor-firmware/blob/49fe64f84c5fc17f5680daaf03b124a2b8f26c3b/crypto/hmac.h) | [4e0d813](https://github.com/trezor/trezor-firmware/commit/4e0d813269a5c527b15b33c6adb6ecb476916165) | 2013-2014 Tomas Dzetkulic<br />2013-2014 Pavol Rusnak  | [MIT](https://spdx.org/licenses/MIT)                        |
| memzero.c | [trezor/trezor-firmware](https://github.com/trezor/trezor-firmware/blob/8ddf799cad4f3e5d6f13d22f21154d2d572c8519/crypto/memzero.c)<br>derived from [jedisct1/libsodium](https://github.com/jedisct1/libsodium/blob/1647f0d53ae0e370378a9195477e3df0a792408f/src/libsodium/sodium/utils.c#L102-L130) | [4e0d813](https://github.com/trezor/trezor-firmware/commit/4e0d813269a5c527b15b33c6adb6ecb476916165)<br>[32385c6](https://github.com/jedisct1/libsodium/commit/32385c6b9a00cb2a83c64cba80e8b5962841cd88) | 2013-2019 Frank Denis                                  | [ISC](https://spdx.org/licenses/ISC)                        |
| memzero.h | [trezor/trezor-firmware](https://github.com/trezor/trezor-firmware/blob/8ddf799cad4f3e5d6f13d22f21154d2d572c8519/crypto/memzero.h)<br/>derived from [jedisct1/libsodium](https://github.com/jedisct1/libsodium/blob/1647f0d53ae0e370378a9195477e3df0a792408f/src/libsodium/sodium/utils.c#L102-L130) | [4e0d813](https://github.com/trezor/trezor-firmware/commit/4e0d813269a5c527b15b33c6adb6ecb476916165)<br/>[32385c6](https://github.com/jedisct1/libsodium/commit/32385c6b9a00cb2a83c64cba80e8b5962841cd88) | 2013-2019 Frank Denis                                  | [ISC](https://spdx.org/licenses/ISC)                        |
| options.h | [trezor/trezor-firmware](https://github.com/trezor/trezor-firmware/blob/8ddf799cad4f3e5d6f13d22f21154d2d572c8519/crypto/options.h) | [4e0d813](https://github.com/trezor/trezor-firmware/commit/4e0d813269a5c527b15b33c6adb6ecb476916165) | 2013-2014 Pavol Rusnak                                 | [MIT](https://spdx.org/licenses/MIT)                        |
| pbkdf2.c  | [trezor/trezor-firmware](https://github.com/trezor/trezor-firmware/blob/49fe64f84c5fc17f5680daaf03b124a2b8f26c3b/crypto/pbkdf2.c) | [fdad317](https://github.com/trezor/trezor-firmware/commit/fdad317d8c5d11bc4734f8cf07b1d589fb475209) | 2013-2014 Tomas Dzetkulic<br />2013-2014 Pavol Rusnak  | [BSD-3-Clause](https://spdx.org/licenses/BSD-3-Clause.html) |
| pbkdf2.c  | [trezor/trezor-firmware](https://github.com/trezor/trezor-firmware/blob/49fe64f84c5fc17f5680daaf03b124a2b8f26c3b/crypto/pbkdf2.h) | [4e0d813](https://github.com/trezor/trezor-firmware/commit/4e0d813269a5c527b15b33c6adb6ecb476916165) | 2013-2014 Tomas Dzetkulic<br />2013-2014 Pavol Rusnak  | [BSD-3-Clause](https://spdx.org/licenses/BSD-3-Clause.html) |
| sha2.c    | [trezor/trezor-firmware](https://github.com/trezor/trezor-firmware/blob/49fe64f84c5fc17f5680daaf03b124a2b8f26c3b/crypto/sha2.c) | [fdad317](https://github.com/trezor/trezor-firmware/commit/fdad317d8c5d11bc4734f8cf07b1d589fb475209) | 2000-2001 Aaron D. Gifford<br />2013-2014 Pavol Rusnak | [BSD-3-Clause](https://spdx.org/licenses/BSD-3-Clause.html) |
| sha2.h    | [trezor/trezor-firmware](https://github.com/trezor/trezor-firmware/blob/49fe64f84c5fc17f5680daaf03b124a2b8f26c3b/crypto/sha2.h) | [4e0d813](https://github.com/trezor/trezor-firmware/commit/4e0d813269a5c527b15b33c6adb6ecb476916165) | 2000-2001 Aaron D. Gifford<br />2013-2014 Pavol Rusnak | [BSD-3-Clause](https://spdx.org/licenses/BSD-3-Clause.html) |

### Used by …

- [bc-shamir](https://github.com/BlockchainCommons/bc-shamir) — Blockchain Common's Shamir Secret Sharing Library

### Derived from…

- [trezor/trezor-firmware/crypto](https://github.com/trezor/trezor-firmware/tree/master/crypto) — Heavily optimized cryptography algorithms for embedded devices, used by both Trezor Core and the Trezor One firmware, from Satoshi Labs ([docs](https://github.com/trezor/trezor-firmware/blob/master/docs/index.md)).

### Dependencies

- autotools - Gnu Build System from Free Software Foundation ([intro](https://www.gnu.org/software/automake/manual/html_node/Autotools-Introduction.html)).

## Contributing

We encourage public contributions through issues and pull-requests! Please review [CONTRIBUTING.md](./CONTRIBUTING.md) for details on our development process. All contributions to this repository require a GPG signed [Contributor License Agreement](./CLA.md).

### Credits

The following people directly contributed to this repository. You can add your name here by getting involved — the first step is to learn how to contribute from our [CONTRIBUTING.md](./CONTRIBUTING.md) documentation.

| Name              | Role                | Github                                            | Email                                 | GPG Fingerprint                                    |
| ----------------- | ------------------- | ------------------------------------------------- | ------------------------------------- | -------------------------------------------------- |
| Christopher Allen | Principal Architect | [@ChristopherA](https://github.com/@ChristopherA) | \<ChristopherA@LifeWithAlacrity.com\> | FDFE 14A5 4ECB 30FC 5D22  74EF F8D3 6C91 3574 05ED |
| Wolf McNally      | Project Lead        | [@WolfMcNally](https://github.com/wolfmcnally)    | \<Wolf@WolfMcNally.com\>              | 9436 52EE 3844 1760 C3DC  3536 4B6C 2FCF 8947 80AE |

## Responsible Disclosure

We want to keep all our software safe for everyone. If you have discovered a security vulnerability, we appreciate your help in disclosing it to us in a responsible manner. We are unfortunately not able to offer bug bounties at this time.

We do ask that you offer us good faith and use best efforts not to leak information or harm any user, their data, or our developer community. Please give us a reasonable amount of time to fix the issue before you publish it. Do not defraud our users or us in the process of discovery. We promise not to bring legal action against researchers who point out a problem provided they do their best to follow the these guidelines.

### Reporting a Vulnerability

Please report suspected security vulnerabilities in private via email to ChristopherA@BlockchainCommons.com (do not use this email for support). Please do NOT create publicly viewable issues for suspected security vulnerabilities.

The following keys may be used to communicate sensitive information to developers:

| Name              | Fingerprint                                        |
| ----------------- | -------------------------------------------------- |
| Christopher Allen | FDFE 14A5 4ECB 30FC 5D22  74EF F8D3 6C91 3574 05ED |

You can import a key by running the following command with that individual’s fingerprint: `gpg --recv-keys "<fingerprint>"` Ensure that you put quotes around fingerprints that contain spaces.

---
title: "Apache Kyuubi Releases"
menu: "releases"
layout: release
type: custompage
---
<!---
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
-->

## To verify Kyuubi releases using GPG:

1.  Download the release apache-kyuubi-X.Y.Z-incubating-source.tgz from a [mirror
    site](https://www.apache.org/dyn/closer.lua/incubator/kyuubi/).
2.  Download the signature file apache-kyuubi-X.Y.Z-incubating-source.tgz.asc from
    [Apache](https://www.apache.org/dyn/closer.lua/incubator/kyuubi/).
3.  Download the [Kyuubi
    KEYS](https://www.apache.org/dyn/closer.lua/incubator/kyuubi/KEYS/KEYS) file.
4.  gpg --import KEYS
5.  gpg --verify apache-kyuubi-X.Y.Z-incubating-source.tgz.asc

## To perform a quick check using SHA-512:

1.  Download the release apache-kyuubi-X.Y.Z-incubating-source.tgz from a [mirror
    site](https://www.apache.org/dyn/closer.lua/incubator/kyuubi/).
2.  Download the checksum apache-kyuubi-X.Y.Z-incubating-source.tgz.sha512 from
    [Apache](https://www.apache.org/dyn/closer.lua/incubator/kyuubi/).
3.  shasum -a 512 apache-kyuubi-X.Y.Z-incubating-source.tgz

All releases of Kyuubi are available from the [Apache release
archive](https://archive.apache.org/dist/incubator/kyuubi/) site.

## License

_The software licensed under [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)._

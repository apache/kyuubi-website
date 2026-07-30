---
title: Apache Kyuubi CVE List
menu:
   main:
      name: "Published CVEs"
      parent: "community"
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

This page lists security fixes that the Kyuubi PMC felt warranted a CVE. If you think something is missing from this list or if you think the set of impacted or fixed versions is incomplete then please ask on security@kyuubi.apache.org.

CVEs are presented in most-recent-first order of announcement.

<!-- These should be sorted as most-recent-first. Please copy this template and fill in as needed.

## [CVE-YYYY-XXXX](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-YYYY-XXXX) Short Description

One paragraph summary goes here. Don't need nuts-and-bolts detail, just enough for a reader to guage applicability to their deployment.

- **Versions affected**:
- **Fixed versions**:
- **Impact**:
- **Reporter**:
- **Reported Date**:
- **Issue Announced**:
-->

## [CVE-2026-52680](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2026-52680) REST batch multipart upload path traversal allows controlled file write

Apache Kyuubi REST batch multipart upload handling uses the client-supplied multipart filename when creating a temporary uploaded resource.
A remote attacker who can access the REST batch upload endpoint can provide path traversal sequences in the filename and cause
the Kyuubi server process to write controlled content outside the intended upload directory, subject to filesystem permissions.

- **Versions affected**: 1.7.0 to 1.11.1
- **Fixed versions**: 1.12.0
- **Impact**: privilege escalation
- **Reporter**: LTSHFWJT
- **Reported Date**: 2026/05/31
- **Issue Announced**: 2026/07/30 ([dev@kyuubi](https://lists.apache.org/thread/b0qx2v8k5v4rrqsh53pb146t7so0lmrk))

## [CVE-2026-23904](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2026-23904) Unrestricted access via Kyuubi engine-ui proxy

Kyuubi Engine UI proxy accepts a host and port from the request path and proxies HTTP requests to that destination.
A remote requester with network access to the proxy can cause the Kyuubi server to send HTTP requests to arbitrary
reachable hosts, resulting in SSRF or open-proxy behavior.

Users are recommended to upgrade to version 1.12.0, which disables the proxy by default. To restore proxied Engine UI,
set `kyuubi.frontend.rest.engine.ui.proxy.enabled=true` and configure allowed target hosts with `kyuubi.frontend.rest.engine.ui.proxy.hosts`.

- **Versions affected**: 1.8.0 to 1.11.1
- **Fixed versions**: 1.12.0
- **Impact**: open redirect
- **Reporter**: Ícaro Torres
- **Reported Date**: 2025/04/08
- **Issue Announced**: 2026/07/29 ([dev@kyuubi](https://lists.apache.org/thread/ps79fcfx49ox9kwgztc5t5bw0tyhck9m))

## [CVE-2025-66518](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-66518) Unauthorized directory access due to missing path normalization

Any client who can access to Apache Kyuubi Server via Kyuubi frontend protocols can bypass server-side config
`kyuubi.session.local.dir.allow.list` and use local files which are not listed in the config.

- **Versions affected**: 1.6.0 to 1.10.2
- **Fixed versions**: 1.10.3
- **Impact**: privilege escalation
- **Reporter**: Hiroki Egawa
- **Reported Date**: 2025/11/21
- **Issue Announced**: 2026/01/05 ([dev@kyuubi](https://lists.apache.org/thread/xp460bwbyzdhho34ljd4nchyt2fmhodl))


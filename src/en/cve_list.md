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

This page lists security fixes that the Kyuubi PMC felt warranted a CVE. If you think something is missing from this list or if you think the set of impacted or fixed versions is incomplete then please ask on security@apache.org.

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

## [CVE-2025-66518](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2025-66518) Unauthorized directory access due to missing path normalization

Any client who can access to Apache Kyuubi Server via Kyuubi frontend protocols can bypass server-side config
`kyuubi.session.local.dir.allow.list` and use local files which are not listed in the config.

- **Versions affected**: 1.6.0 to 1.10.2
- **Fixed versions**: 1.10.3
- **Impact**: privilege escalation
- **Reporter**: Hiroki Egawa
- **Reported Date**: 2025/11/21
- **Issue Announced**: 2026/01/05 ([dev@kyuubi](https://lists.apache.org/thread/xp460bwbyzdhho34ljd4nchyt2fmhodl))


---
title: Kyuubi Usage
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
Kyuubi provides a pure SQL gateway through Thrift JDBC/ODBC interface for end-users to manipulate large-scale data with pre-programmed and extensible Spark SQL engines.

We are aiming to make Kyuubi an "out-of-the-box" tool for data warehouses and data lakes.

This "out-of-the-box" model minimizes the barriers and costs for end-users to use Spark at the client side.

At the server-side, Kyuubi server and engines' multi-tenant architecture provides the administrators a way to achieve computing resource isolation, data security, high availability, high client concurrency, etc.

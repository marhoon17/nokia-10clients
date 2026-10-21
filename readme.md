# Nokia 10-Client Containerlab Lab

A virtual network lab built with [Containerlab](https://containerlab.dev/) featuring a single **Nokia SR Linux** router connected to **10 Linux clients** in a star topology. This lab is ideal for testing routing, ACLs, QoS, traffic generation, or any scenario requiring multiple endpoints behind a Nokia data plane.

## 📐 Topology





| Node         | Role       | Image                     | Kind            |

|--------------|------------|---------------------------|-----------------|

| `nokia-router` | Router   | `ghcr.io/nokia/srlinux`   | `nokia\_srlinux` |

| `client1..10`  | Clients  | `alpine:latest`           | `linux`         |



Each client is auto-configured via the topology `exec` block with a unique `10.0.x.1/24` address on `eth1`.



\## 📋 Prerequisites



\- \*\*Linux host\*\* (bare metal or VM) — Containerlab does not run on macOS/Windows natively

\- \*\*Docker\*\* (or Podman) installed and running

\- \*\*Containerlab\*\* installed — \[installation guide](https://containerlab.dev/install/)

\- \*\*\~4 GB RAM\*\* and \*\*\~10 GB free disk space\*\* (SR Linux images are large)

\- \*\*Root or sudo\*\* access (needed to create network namespaces and veth pairs)

\- \*\*Sufficient kernel limits\*\* for veth pairs (rarely an issue, but see Troubleshooting)



Verify installation:



```bash

containerlab version

docker --version


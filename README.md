# HyperDX: ClickHouse-proxy Data-plane SSRF

CVE pending (reserved).

An authenticated low-privilege HyperDX user can create a connection whose host points at an
internal address, then read it back through the ClickHouse proxy. The server fetches the
internal address, returns the response body to the attacker, and forwards attacker-supplied
headers, so the request reaches internal services and the cloud metadata endpoint.

- Affected: @hyperdx/api 2.40.0 and earlier
- CWE-918 (Server-Side Request Forgery)
- CVSS 3.1: 9.1 Critical (AV:N/AC:L/PR:L/UI:N/S:C/C:H/I:L/A:L)

Full write-up and proof of concept: **[HR-hyperdx-clickhouse-proxy-ssrf.pdf](HR-hyperdx-clickhouse-proxy-ssrf.pdf)**

## Disclaimer

This proof of concept is for authorized security testing and education only.
Test only systems that you own or have explicit permission to test. The author
takes no responsibility for misuse.

# Bluelight Phishing Campaign — Threat Intelligence Investigation

An independent investigation of a live multi-country phishing campaign, conducted through passive analysis of unsolicited emails received between August and September 2026.

## Overview

What began as a spam email claiming a failed Google Cloud storage payment evolved into a weeks-long investigation uncovering a sophisticated, multi-layered phishing operation with infrastructure spanning eight countries.

## Key Findings

- **Sending infrastructure** — A pool of sb0XX.store domains bulk-registered on Namecheap within 19 seconds on May 5 2026, serving as a centralized SPF and DKIM hub for the entire campaign
- **IP pool** — 43 OVH IP addresses (predominantly Gravelines, France) managed through api.netresolve.help, including two dedicated contiguous subnet blocks used as web servers
- **Redirect chain** — A multi-hop Traffic Distribution System routing victims through bluelightlenzo.com (Bangkok, Thailand) and solutionfornow.com (Google Cloud, Kansas City) before reaching the credential harvesting endpoint
- **Subdomain takeovers** — Multiple dangling CNAME attacks identified affecting organizations across four countries, including a major UK retailer, a US fitness chain, a French financial newspaper, a French election technology platform, and a Canadian mobile carrier
- **Attribution** — Developer comments in Darija (Moroccan Arabic dialect) found in Google Storage lure pages suggest possible Moroccan origin. Infrastructure prepared three months before the first observed email.

## Reports

| Document | Description |
|----------|-------------|
| [Bluelight 1](Bluelight_1.md) | Full header analysis, DNS investigation, and sending infrastructure discovery |
| [Bluelight 2](Bluelight_2.md) | Comparative analysis of a second campaign sample |
| [Dangling CNAME Attacks](Dangling_CNAMEs.md) | Subdomain takeover findings and full infrastructure diagram |

## Methodology

All analysis was conducted passively using command line tools — curl, dig, whois, and dkimverify — against publicly accessible infrastructure. No systems were accessed without authorization. Affected organizations were notified through responsible disclosure.

## Tools Used

- `dig` — DNS forward and reverse lookups, TXT and CNAME record analysis
- `curl` — HTTP redirect chain tracing, infrastructure attribution via ipinfo.io
- `dkimverify` (dkimpy) — DKIM signature verification
- `whois` — Domain registration and registrar investigation
- Bash scripting — Bulk IP attribution and subnet analysis
- VM for network analysis of malicious pages.

## Responsible Disclosure

Findings were reported to:
- Affected organizations via security contact emails
- GoDaddy abuse team
- Namecheap abuse team
- Cloudflare abuse team

## Author

Crush | [GitHub](https://github.com/Crush-pixel)

*CompTIA A+ · Network+ · Security+ · ITIL 4 · AWS Cloud Practitioner*

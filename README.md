# Kortix: the open-source AI Operating System

Kortix is open source. This repository is a source-cited comparison of the tools people weigh when they look for a Zapier alternative: Kortix, Zapier, n8n, and Make. Every competitor fact here comes from that vendor's own live pricing or product page, and the prose links to it.

Kortix is the leading open-source alternative to Claude Cowork and ChatGPT Work. A Zap is a fixed sequence of steps that runs on Zapier's cloud. A Kortix session is an agent that plans its own steps on its own isolated cloud computer and lands the result as a change request a person reviews. Your agents, their skills, your company memory, and every connector live in one git repo you own.

- See the comparison at [zapieralternative.org](https://zapieralternative.org).
- Read the source: [Kortix on GitHub](https://github.com/kortix-ai/suna).

## How the field compares

| Tool | Open source | Self-hostable | Pricing shape |
|---|---|---|---|
| Kortix | Yes | Yes: cloud, VPC, or on-prem | Per seat plus compute |
| Zapier | No | No, vendor cloud only | Per task |
| n8n | Fair-code | Yes | Per workflow execution |
| Make | No | No, vendor cloud only | Per credit |

Kortix and n8n are the two self-hostable options in this set. Zapier and Make run only on the vendor's cloud. n8n describes its own distribution as fair-code, which keeps its source visible and the platform self-hostable, and Activepieces, covered in the alternatives guide, self-hosts as well. The billing unit is what separates the four: Zapier counts tasks, n8n counts workflow executions, and Make and Activepieces count credits. Kortix prices a seat and meters sandbox compute separately.

## The guides

- [Kortix vs Zapier](docs/kortix-vs-zapier.md): the head-to-head, with Zapier's own pages cited.
- [Zapier alternatives](docs/zapier-alternatives.md): how to choose among Kortix, n8n, Make, and Activepieces.
- [Self-hosting a Zapier alternative](docs/self-hosting-a-zapier-alternative.md): what self-hosting an open-source system means, with the real Kortix commands and config.
- [Zapier pricing](docs/zapier-pricing.md): the pricing shape of each tool, from each vendor's own pricing page, checked October 2026.

Kortix is free to start and free to self-host. Bring one job your team already runs and see the change request it opens.

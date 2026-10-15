# Zapier alternatives: how to choose among Kortix, n8n, Make, and Activepieces

The right Zapier alternative depends on what kind of work you are moving. Kortix is the open-source AI Operating System for open-ended work an agent runs on its own machine, while n8n, Make, and Activepieces are automation tools built around a workflow or a flow. Each one is a different unit of work, and the unit decides the choice more than the app count does.

## The options at a glance

| Tool | Open source | Self-hostable | Pricing shape |
|---|---|---|---|
| Kortix | Yes | Yes: cloud, VPC, or on-prem | Per seat plus compute |
| n8n | Fair-code | Yes | Per workflow execution |
| Make | No | No, vendor cloud only | Per credit |
| Activepieces | Yes | Yes, cloud or on-prem | Per credit |

Every vendor fact on this page comes from that vendor's own pages, and the pricing shapes are from each vendor's pricing page, checked October 2026.

## Kortix

Kortix is the open-source AI Operating System. Your agents, their skills, your company memory, and every connector live in one git repo you own, and each session runs on its own isolated cloud computer ([Kortix docs](https://kortix.com/docs)). Kortix is open source, and self-host is free. The unit of work is a session: give an agent a job in plain language and it plans the steps, uses the tools you connect, and lands the result as a change request a person reviews.

The Kortix connector layer reaches 3,000+ apps in a click, plus MCP, OpenAPI, Postman, GraphQL, and raw HTTP, with connector credentials brokered server-side and never entering the machine. Kortix is model-agnostic, so a team picks the model per agent, per session, or per message and brings its own keys. Each tool call can be set to allow, ask, or block.

## n8n

n8n is a workflow automation tool that combines a visual canvas with JavaScript and Python, and it runs self-hosted or on n8n Cloud ([n8n](https://n8n.io/)). Its own repository describes it as a fair-code platform with 1500+ integrations and 9,000+ workflow templates, and the Community Edition is available to self-host ([n8n on GitHub](https://github.com/n8n-io/n8n)).

n8n's unit is the workflow execution. Its pricing page states that "an execution is a single run of your entire workflow," and the run counts once no matter how many steps it contains ([n8n pricing](https://n8n.io/pricing/)). Cloud plans start at $20/mo billed annually for 2.5K executions, and the Business plan is self-hosted only.

## Make

Make is a hosted visual automation tool. You build a scenario in a drag-and-drop interface that connects 3,500+ apps, and each module action in a scenario consumes credits ([Make pricing](https://www.make.com/en/pricing)). Make bills per credit, with a Free plan, paid Core, Pro, and Teams tiers, and an Enterprise tier on request. It runs on Make's cloud, and an on-prem agent is offered only on the Enterprise plan.

Make is a fit when you want a visual drag-and-drop builder and a broad catalog of pre-built app modules, and you are content to run on the vendor's infrastructure.

## Activepieces

Activepieces is an open-source automation tool that puts a flow builder, agents, tables, and MCP access in one workspace, with 760+ apps ([Activepieces](https://www.activepieces.com/)). It runs on the vendor's cloud or on your own servers, and its Enterprise page offers a fully air-gapped deployment. Activepieces is open source, and it self-hosts.

Activepieces bills per credit, with a Free plan, Plus at $20 per month, and Team at $200 per month ([Activepieces pricing](https://www.activepieces.com/pricing)). The unit is a flow or an agent run, and the credit count sets the ceiling.

## How to choose

- Pick **Kortix** when the job is open-ended work whose steps you cannot list in advance, or when the agents, skills, memory, credentials, and model need to live in a repo and an infrastructure you own.
- Pick **n8n** when the job is a fixed workflow and you want a visual canvas with code beside it, and you will self-host or buy a cloud plan priced per execution.
- Pick **Make** when the job is a visual scenario across a wide app catalog and you are happy to run on the vendor's cloud.
- Pick **Activepieces** when the job is a flow or an agent and you want an open-source tool you can self-host or run air-gapped.

Zapier itself stays a reasonable choice for a small, fixed flow that already has a connector, because its 9,000+ apps and task-based billing are easy to start with ([Zapier pricing](https://zapier.com/pricing)).

## FAQ

**Which Zapier alternatives are open source?**

Kortix and Activepieces are open source. Kortix and Activepieces both self-host, and both run on a vendor cloud as well. n8n describes its own distribution as fair-code and also self-hosts.

**Which Zapier alternative is cheapest to try?**

Kortix is free to start and free to self-host, Activepieces has a free plan with no card, Make has a free plan, and n8n offers a free trial on its cloud plus a self-hosted Community Edition. The full free-tier comparison is in the pricing guide on this repository.

**Can I self-host a Zapier alternative?**

Yes. Kortix, n8n, and Activepieces all self-host. Make runs on the vendor's cloud, with an on-prem agent only on its Enterprise plan. The self-hosting guide on this repository covers what running one means and the real Kortix commands.

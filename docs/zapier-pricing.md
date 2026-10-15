# Zapier pricing: how each alternative bills, checked October 2026

Zapier bills per task, and the open-source alternatives bill on different units: Kortix prices a seat and meters compute separately, n8n bills per workflow execution, and Make and Activepieces bill per credit. The unit decides which tool costs less at your volume, more than the headline number does. Every figure on this page is quoted from the vendor's own pricing page and was checked October 2026.

## The billing units at a glance

| Tool | Billing unit | Free tier | Pricing shape |
|---|---|---|---|
| Kortix | Seat plus compute | Yes, 1 project | Flat seat with pooled credits |
| Zapier | Task | Yes, limited tasks per month | Tiers by task volume |
| n8n | Workflow execution | Community edition, self-hosted | Cloud tiers by execution volume |
| Make | Credit | Yes, limited credits per month | Tiers by monthly credits |
| Activepieces | Credit | Yes, limited credits per month | Flat monthly with a credit cap |
| Gumloop | Credit | No free tier listed | Flat Pro plus custom Enterprise |

The dollar figures move, so they stay in the notes on this page rather than in this table. Each is dated to October 2026 and linked to its source.

## Kortix

Kortix is the open-source AI Operating System. Its pricing page states that the Free plan "includes 200 credits each month for sandbox compute and 1 project," and that the Team plan is "$40/seat/month" with "2,500 pooled credits per seat" ([Kortix pricing](https://kortix.com/pricing)). Agent Computer compute is billed per second, per resource, which works out to about $0.20/hour for the default 2 vCPU / 4 GiB / 20 GiB machine and $0 while stopped.

Two things set the Kortix pricing shape apart. The seat is a flat monthly fee that includes credits, so a team tops up only when compute or an optional managed model exhausts the pooled balance. And model access is unbundled: bring your own API key or connect a ChatGPT subscription and pay your model provider directly. Self-host is free, so a team that runs its own infrastructure pays for the server and the model, not for a plan.

## Zapier

Zapier bills per task. Its pricing page states that "every step in a Zap and every external connector call uses tasks," and that tasks are shared across the account ([Zapier pricing](https://zapier.com/pricing)). The Free plan carries 100 tasks per month and two-step Zaps. Professional, Team, and Enterprise scale by task tier, with a switch to pay-as-you-go at the limit unless you move up a tier or turn it off. Zapier does not publish a self-host option, so the plan is the only way to run a Zap.

## n8n

n8n bills per workflow execution. Its pricing page states that "an execution is a single run of your entire workflow," and that the run counts once "no matter how many steps are in the workflow" ([n8n pricing](https://n8n.io/pricing/)). Cloud plans start at $20/mo billed annually for 2.5K executions, $50/mo for 10K, and $800/mo for 40K on the Business plan, which is self-hosted only. Enterprise is custom. The Community Edition is self-hosted, so a team that runs the volume itself pays for a server and its own support.

The execution model is the reason a long workflow is cheaper here than on a per-step tool: a hundred-step run is still one execution. The trade-off is that the unit is fixed by the workflow, not by the work inside it.

## Make

Make bills per credit. Its pricing page states that "each action your scenario performs consumes a certain number of credits," and that most actions use one ([Make pricing](https://www.make.com/en/pricing)). The Free plan includes 1,000 credits per month, and the paid tiers are Core from $9/mo, Pro from $16/mo, and Teams from $29/mo, each shown with a 15% annual discount, plus a custom Enterprise tier. Make runs on Make's cloud, and an on-prem agent for local networks is offered only on Enterprise.

## Activepieces

Activepieces bills per credit across a flow, agent, and table workspace. Its pricing page lists a Free plan with 1,000 credits a month, Plus at $20 per month with 10,000 credits, and Team at $200 per month with 50,000 credits, plus a custom Ultimate tier ([Activepieces pricing](https://www.activepieces.com/pricing)). Activepieces is open source and self-hosts on your own servers, and the Enterprise page offers a fully air-gapped deployment.

## Gumloop

Gumloop is a hosted agent builder and bills per credit. Its pricing page lists a Pro plan that "starts at $37 / month" and a custom Enterprise tier ([Gumloop pricing](https://www.gumloop.com/pricing)). It runs on Gumloop's cloud, so there is no self-host option and no free tier listed on the page.

## How the units compare

Task-based billing charges for each action a flow performs, so a busy flow costs more as it does more. Execution-based billing charges once per run, so the cost follows how often the flow runs rather than how large it is. Credit-based billing sits between the two: a credit is a unit of work a module or agent consumes, and the plan sets the monthly ceiling. Kortix's seat-plus-compute shape charges for the machine time and the tokens the work actually uses, which fits open-ended agent work better than a per-step count does.

## FAQ

**Is Zapier cheaper than the open-source alternatives?**

It depends on the unit. A small fixed flow on Zapier's free task allowance can cost nothing to run. A high-volume or long-running job usually costs less on n8n, where a whole workflow run is one execution, or on Kortix, where a free tier and free self-host cover the start and the seat covers the team. The figures on this page were checked October 2026 and change, so confirm them on each vendor's pricing page.

**Do any of these have a free tier?**

Kortix has a free tier with 1 project, Zapier has a free plan with a limited task count, Make and Activepieces each have a free plan with a limited credit count, and n8n offers a self-hosted Community Edition at no cost. Gumloop lists no free tier on its pricing page.

**What is the difference between a task, an execution, and a credit?**

A task is one action a flow performs, and Zapier bills per task. An execution is one full run of a workflow, and n8n bills per execution regardless of step count. A credit is a unit of work a module or agent consumes, and Make and Activepieces bill per credit.

**Can I self-host any of these to avoid the pricing?**

Yes for Kortix, n8n, and Activepieces, which all self-host. Kortix self-host is free. Make and Gumloop run on their own clouds, and Make offers an on-prem agent only on Enterprise.

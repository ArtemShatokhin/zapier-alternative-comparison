# Kortix vs Zapier: an open-source AI Operating System or a hosted workflow tool

Zapier is a hosted workflow tool that runs fixed Zaps on Zapier's cloud, and Kortix is the open-source AI Operating System that runs agent sessions on their own isolated cloud computers. The unit of work decides the choice. A Zap is a sequence of steps you define in advance. A Kortix session plans its own steps, uses the tools you connect, and lands the result as a change request a person reviews.

## What Zapier is

Zapier is the hosted workflow-automation incumbent. Its own about page calls it "the leader in easy automation" and reports that more than 2 million businesses automate with it ([Zapier about](https://zapier.com/about)). You build a Zap from a trigger and one or more actions, and Zapier runs it on its cloud. Its pricing page describes a Zap as "an automated workflow that connects your apps and services together" and states that every step and every connector call uses tasks ([Zapier pricing](https://zapier.com/pricing)).

Zapier connects 9,000+ apps and includes a visual editor, filters, paths, and code steps. The Free plan carries 100 tasks per month and two-step Zaps, and the paid plans (Professional, Team, and Enterprise) scale by task tier. There is no self-host option: a Zap runs where Zapier runs it.

## What Kortix is

Kortix is the open-source AI Operating System. Your agents, their skills, your company memory, and every connector live in one git repo you own, and every session runs on its own cloud computer ([Kortix docs](https://kortix.com/docs)). Kortix is open source, so a team can read, fork, and audit the code, and self-host is free. Each session works on its own branch, and a connected trigger can start one from a cron schedule or a signed webhook with nobody present.

The Kortix connector layer reaches 3,000+ apps in a click, plus MCP, OpenAPI, Postman, GraphQL, and raw HTTP. Connector credentials are brokered server-side and never enter the machine. Kortix is model-agnostic: pick the model per agent, per session, or per message, bring your own API key, or sign in with the ChatGPT subscription you already pay for. Each tool call can be set to allow, ask, or block, and agent work reaches the default branch only through a change request a person reads as a diff.

## Kortix and Zapier side by side

| Dimension | Kortix | Zapier |
|---|---|---|
| Open source | Yes | No |
| Unit of work | An agent session on its own machine | A Zap of fixed steps |
| Where it runs | Cloud, VPC, or on-prem | Zapier's cloud only |
| Model choice | Any model, your keys | No model you bring |
| Integrations | 3,000+ apps, plus MCP and HTTP | 9,000+ apps |
| Pricing shape | Per seat plus compute | Per task |

Kortix reaches 3,000+ apps, and Zapier reaches 9,000+ apps, so Zapier lists more pre-built connectors. Kortix closes that gap with MCP, OpenAPI, Postman, GraphQL, and raw HTTP, which reach an API that has no Zapier connector. The other rows follow from the unit of work: a Zap runs the same steps every time, and a session decides its own steps and can be stopped at each call.

## Where Zapier fits

Zapier is a strong choice when the job is a fixed, linear flow: the same steps, in the same order, on a schedule or a webhook. Its 9,000+ apps mean the connector you need often exists, and the visual editor lets a non-developer change a step without touching code. Task-based billing is easy to predict for a simple automation that moves a small, steady volume of records.

## Where Kortix does the work

Kortix is the choice when the job is open-ended: research, a report, a fix, a campaign, or any task whose steps you cannot list in advance. You give an agent a job in plain language from the web app, Slack, Microsoft Teams, email, the CLI, or the API, and it plans and runs the steps itself on its own machine. The configuration it runs from is text you own, so a team can grep the whole company, diff any change, and roll any part of it back.

The gate is the other difference. In Kortix, each connector call can be set to allow, ask, or block, and an Ask holds the call until a person approves it and then the agent resumes. A person with the merge permission reviews the change request before the work reaches the default branch.

## When to pick which

Pick Zapier when the job is a fixed flow and a connector for each app already exists. It is the simpler choice for deterministic integrations that run on a clock.

Pick Kortix when the job is open-ended work whose steps you cannot write down in advance, or when the configuration, the credentials, and the model need to live in an infrastructure you control. Kortix is free to start and free to self-host.

## FAQ

**Is Kortix open source?**

Yes. Kortix is open source, so you can read, fork, and audit the code, and self-host is free. Zapier is a closed hosted product with no self-host option.

**Can Kortix replace Zapier?**

Kortix runs open-ended agent work on its own machine and reaches apps through connectors, MCP, and HTTP, so it can take over the jobs you cannot express as a fixed Zap. A fixed linear flow that already has a connector stays a good fit for Zapier.

**How does Kortix pricing compare to Zapier?**

Zapier bills per task. Kortix prices a seat that includes pooled credits and meters sandbox compute separately, so the cost follows the work an agent does rather than the number of steps a flow runs. The pricing guide on this repository compares the shapes.

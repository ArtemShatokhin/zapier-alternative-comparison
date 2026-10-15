# Self-hosting a Zapier alternative: what it means and how to start with Kortix

Self-hosting a Zapier alternative means you run the automation software on a server you control instead of on the vendor's cloud. Kortix is the open-source AI Operating System, and self-host is free: the full platform runs on your box as one Docker Compose stack, with the agents, skills, memory, connectors, and triggers still living in a git repo you own. Zapier and Make do not offer this. n8n and Activepieces do, and Kortix is the one that runs open-ended agent sessions rather than only fixed flows.

## What self-hosting changes

A hosted tool keeps your flows, credentials, and execution history in the vendor's account, and you reach it through the vendor's UI. A self-hosted tool inverts that. The server, the database, the credentials store, and the model keys are yours, and an update is a decision you make rather than one the vendor pushes. You take on the operations the vendor used to carry: DNS, TLS certificates, backups, and the upgrade path.

For a Zapier-style tool, three things move when you self-host:

- **The data.** Flow definitions, run history, and credential material sit in your database and your secret store.
- **The credentials.** Connector credentials are stored and brokered on your instance.
- **The model.** You hold the model provider key and choose which model the work runs on.

The trade-off is real: a self-hosted stack is a server you now operate. Kortix keeps the operational surface to one Compose project and a CLI.

## What a self-hosted Kortix instance is

A self-hosted Kortix instance is the full Kortix platform on a server you control: one Docker Compose stack that the `kortix self-host` CLI installs, configures, and updates ([Kortix self-hosting](https://kortix.com/docs/host)). One Compose project, named `kortix-<instance>`, holds every service: the web frontend, the API, the LLM gateway, a database migration job, a daily updater, the database and storage services, and Caddy for TLS in domain mode.

Two facts matter before you start. Sessions run on a cloud sandbox provider rather than on the server, so the instance must be reachable from the internet for those sandboxes to call back. And you need a sandbox provider key (Daytona, Platinum, or E2B) and a model provider key, which you add in the web app after the first sign-in.

The host needs a Linux server with a public IP, DNS `A` or `AAAA` records for the domain and its `api.` subdomain, ports 80 and 443 open, and a wildcard record for sandbox previews.

## The Kortix self-host commands

Install the CLI, then initialize and start the stack. These commands are the shipped ones from the self-hosting and quickstart docs.

```bash
# Install the Kortix CLI (macOS and Linux on x86_64 and arm64; WSL on Windows)
curl -fsSL https://kortix.com/install | bash

# Initialize the stack with a domain and an admin email, then start it
kortix self-host init --domain kortix.example.com --admin-email you@example.com
kortix self-host start

# Answer the setup questions again and apply the answers
kortix self-host configure
kortix self-host start

# Check the instance and fix every failing check
kortix self-host doctor
```

On a bare server, the Kortix bootstrap installs Docker and the CLI, then starts the stack with a TLS certificate. On a server that already has Docker, use the by-hand path: install the CLI, run `kortix self-host init` with the domain and admin email, then run `kortix self-host start`.

To evaluate the platform on your own machine with no domain, `kortix self-host init --tunnel cloudflare` then `kortix self-host start` opens the web app at `http://localhost:13737` and publishes the API through a Cloudflare tunnel. Domain mode is the production setup.

## The config you own

The point of self-hosting Kortix is that the configuration is a repo you keep. `kortix.yaml` at the project root declares the machine image, the connectors, the triggers, and the secret names and grants. Agents and skills are markdown files beside it. A trigger starts a session with nobody present, on a cron schedule or a signed webhook:

```yaml
# kortix.yaml
triggers:
  - slug: daily-digest
    type: cron
    cron: '0 0 9 * * 1-5'
    prompt: Summarize yesterday's support tickets and open a change request with the digest.
```

An agent is a markdown file plus a block in the same file that says what it may reach:

```yaml
# kortix.yaml
agents:
  support-triage:
    file: agents/support-triage.md
    connectors: all
```

The same `kortix.yaml` runs on a self-hosted instance and on the managed cloud, so a job you build locally moves to your own server without a rewrite.

## Self-host the same job on a workflow tool

The workflow tools self-host too, and the unit you run is different. n8n runs a fixed workflow and self-hosts its Community Edition, and its cloud plans bill per execution ([n8n on GitHub](https://github.com/n8n-io/n8n)). Activepieces self-hosts its flow, agent, and table workspace on your servers or air-gapped ([Activepieces](https://www.activepieces.com/)). Both are a good fit when the job is a flow you can draw. Kortix is the choice when the job is open-ended work an agent should plan and run on its own machine, with the whole configuration in the repo.

## FAQ

**Is self-hosting Kortix free?**

Yes. Kortix is open source and self-host is free. You pay your own server and your own model provider, and the sandbox provider key you supply starts the sessions.

**Does Zapier offer self-hosting?**

No. Zapier runs on Zapier's cloud only, and a Zap runs where Zapier runs it ([Zapier pricing](https://zapier.com/pricing)). Make runs on Make's cloud, with an on-prem agent offered only on its Enterprise plan ([Make pricing](https://www.make.com/en/pricing)).

**What does a self-hosted Kortix instance need?**

A Linux server with a public IP, DNS records for the domain and its API subdomain, ports 80 and 443 open, a sandbox provider key, and a model provider key. The instance must be reachable from the internet so its sessions' sandboxes can call back.

**Does the whole configuration move to my server?**

Yes. Agents, skills, memory, connectors, and triggers are files in the git repo, and `kortix.yaml` declares the machine image, connectors, triggers, and secret names and grants. The same repo runs on a self-hosted instance and on the managed cloud.

---
sidebar_position: 2
---

# Birthday & Anniversary Bot

The `Hahams` slack bot that sends messages for birthdays and anniversaries is done through executing a Github Action every night.

Note: The Github Actions have their cron job time set as `6` and `7` because it accounts for the timezone difference.

### Authentication

Locally, these two actions use environment variables injected via the CLI (as described in the Quick Start section). However, this isn't possible in production and therefore alternate strategies are used.

The birthday action uses the firebase admin sdk & setting it up is through the `google-github-actions/setup-gcloud@v0` github action. This requires the `GCP_SA_KEY` saved as an environment variable. 

The anniversary action uses the firebase client sdk instead as passing environment variables is done automatically through Github.

### Execution

View the workflow files that run the github actions.

- [Birthday Action](https://github.com/acmutd/leadership/blob/main/.github/workflows/birthday.yml)
- [Anniversary Action](https://github.com/acmutd/leadership/blob/main/.github/workflows/anniversary.yml)
---
sidebar_position: 3
---

# Environment Variables

The following Environment Variables are defined in Doppler and exist for the listed use cases. Differences in the environment variable values between local and production environments are also noted below.

### Env Info

Note: The variables are listed in alphabetical order.

- `ACM_CORE_BASE_URL`

This is the base url for the production [ACM Core API](https://github.com/acmutd/portal-backend). Only the `/challenge/send-email` endpoint is used in this project.

- `ACM_CORE_BASE_URL_2`

This is the base url for when running the [ACM Core API](https://github.com/acmutd/portal-backend) locally. Used for manually testing changes to the functionality shared between the two projects.

- `ACM_SLACK_SHOUTOUT_CHANNEL`

This is the webhook url for the `#shoutouts` channel in the ACM Slack workspace.

- `ACM_SLACK_SHOUTOUT_CHANNEL_2`

This is the webhook url to send DM messages to [Harsha Srikara](https://github.com/harshasrikara). Used for testing slack message functionality before promoting features to production.

- `DEV_DOPPLER_TOKEN`

This is the Doppler [Service Token](https://docs.doppler.com/docs/service-tokens) to fetch the `dev` root config. Used when running the project locally.

- `FIREBASE_CLIENT_EMAIL`

Service account email for the firebase admin sdk.

- `FIREBASE_PRIVATE_KEY`

Private key to grant access to the firebase admin sdk.

- `GOOGLE_ID`

Env variable from the `Cloudflare Access` GCP Project to allow for sign in with google. Used by NextAuth.

- `GOOGLE_SECRET`

Env variable from the `Cloudflare Access` GCP Project to allow for sign in with google. Used by NextAuth.

- `LEADERSHIP_RSA_PUBLIC_KEY`

Used to decrypt Authorization JWTs that are passed along as a header for the GraphQL API.

- `LEADERSHIP_RSA_PRIVATE_KEY`

Used to encrypt Authorization JWTs that are passed along as a header for the GraphQL API.

- `NEXT_PUBLIC_FIREBASE_API_KEY` & other `NEXT_PUBLIC_` variables

Initialization variables for the firebase client sdk.

- `NEXT_PUBLIC_SENTRY_DSN`

Sentry DSN to send captured exceptions to Sentry. Currently not used in the project.

- `NEXTAUTH_URL`

Set to `http://localhost:3000/` in the `dev` config & `https://leadership.acmutd.co/` in the `prd` config. Used by NextAuth.

- `NEXTSECRETS_REDIS_URL` & `NEXTSECRETS_TOKEN`

URL & Access Token for redis cache. Hosted on UpStash. Not used in the project.

- `PROD_DOPPLER_TOKEN`

This is the Doppler [Service Token](https://docs.doppler.com/docs/service-tokens) to fetch the `prd` root config. Used when running the project on vercel.

- `SLACK_TOKEN`

Used for accessing the Slack API to find user's slack id's given their name. Required for being able to `@` a user in slack.

- `TEMPLATE_ID_RECEIVER`

Sendgrid dynamic template ID for the email sent to the person given a shoutout.

- `TEMPLATE_ID_SENDER`

Sendgrid dynamic template ID for the email sent to the person giving a shoutout.
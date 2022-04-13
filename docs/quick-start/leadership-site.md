---
sidebar_position: 1
---

# Leadership Site

To get started with running a version of the leadership site locally follow these steps:

### Setup

Before going through these steps make sure that you have access to [Doppler](https://doppler.com). You can get access by signing in with your ACM account. Additionally make sure to install the [Doppler CLI](https://docs.doppler.com/docs/cli).

- Clone the repo `git clone https://github.com/acmutd/leadership.git`
- Run `cd leadership` to enter the leadership site directory
- Run `doppler login` and sign in with your ACM account when prompted to.
- Run `doppler setup` and select the `leadership` project with the `dev` config in the cli prompts.

These steps will setup the project locally with all the environment variables needed.

### Launch
- Run `npm install`
- Run `npm run dev`

:::caution
If you are using Windows, running `npm run dev` may cause some errors. By default this project is setup to inspect server side logs and print them to the terminal window running the application. If there are any issues remove the `NODE_OPTIONS='--inspect'` from the scripts section of the `package.json` file for `npm run dev`.
:::

After running these steps you should be able to open up `http://localhost:3000` and view the leadership site!
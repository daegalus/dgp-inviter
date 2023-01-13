# Instrucitons for dealing with Fly.io for DGP

This is the repo that houses the inviter script.

It is hosted in `fly.io` using the same credentials as in `heroku`.

You need to install `flyctl` locally, there are instructions here: [https://fly.io/docs/hands-on/install-flyctl/](https://fly.io/docs/hands-on/install-flyctl/)

Once its installed, you can follow these instructions to signin: [https://fly.io/docs/hands-on/sign-in/](https://fly.io/docs/hands-on/sign-in/)

Once signed in, if you just need to redeploy, just type `flyctl deploy`

If you need to make any environment changes, edit the `fly.toml` file's env section. Same with ports, just edit the PORT env and then further down, any mentions of `internal_port`. (also change the `Dockerfile` to `EXPOSE` a different port.)

If you need to update the `SLACK_TOKEN` secret, it can be done with the following command: `flyctl secrets set SLACK_TOKEN=<new token>`

If you lose the token, either re-generate it and set it, or ping @Daegalus (yulian on DGP slack), he has it stored in his password manager.

Everything else, like restarts, monitoring, checking logs, etc, can be viewed on the web dashboard: [https://fly.io/apps/dgp-slack-inviter](https://fly.io/apps/dgp-slack-inviter)

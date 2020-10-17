# Slack Webhook CircleCI Orb [![CircleCI Orb Version](https://img.shields.io/badge/endpoint.svg?url=https://badges.circleci.io/orb/adamu/slack-webhook)](https://circleci.com/orbs/registry/orb/adamu/slack-webhook)

## Setup

1. [Create a webhook](https://api.slack.com/messaging/webhooks).
2. [Generate a JSON payload](https://app.slack.com/block-kit-builder).
3. Place the webhook in a [CircleCI environment variable](https://circleci.com/docs/2.0/env-vars/) (`SLACK_WEBHOOK` by default, but customizable).
4. Call the orb:
   ```yml
   slack-webhook/send-message:
     json-payload: |
       {
         "blocks": [
           {
             "type": "section",
             "text": {
               "type": "mrkdwn",
               "text": "Hello from <https://github.com/adamu|@adamu>'s `slack-webhook` CircleCi orb! 👋"
             }
           }
         ]
       }
   ```

## Usage

The `json-payload` argument must always be provided.

There are three ways to provide the webhook URL:
1. Via the `SLACK_WEBHOOK` environment variable.
2. Via a custom environment variable. Provide the name with the `webhook-url-env-var` parameter.
3. Directly to the `send-message` command with the `webhook-url` parameter.

See the full examples on the orb's [CircleCI Orb Repository listing](https://circleci.com/developer/orbs/orb/adamu/slack-webhook#usage-examples).

## Changelog

See the [CHANGELOG](CHANGELOG.md).

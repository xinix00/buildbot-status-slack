Slack.io status plugin for Buildbot
===================================

This Buildbot plugin sends messages to a Slack.io channel when each build finishes with a handy link to the build results.

This plugin is based on the buildbot-status-hipchat plugin created by the dev team at http://www.pricingassistant.com/ ; Contributions are welcome!

Install
=======

Copy slack.py next to your master.cfg file

Then in your master.cfg, add the following:

```
import slack
c['status'].append(slack.slackStatusPush("YOUR_SLACK_TOKEN", "SLACK_CHANNEL_NAME"))
```

If you Buildbot web frontend doesn't know its public address it will use "localhost" in its links. You can change this:

```
import slack
c['status'].append(slack.slackStatusPush("YOUR_SLACK_TOKEN", "SLACK_CHANNEL_NAME", "buildbot.mycompany.com"))
```

If you want to specify a builder name you can add it to the master.cfg like this:

```
import slack
c['status'].append(slack.SlackStatusPush("YOUR_SLACK_TOKEN", "SLACK_CHANNEL_NAME", "buildbot.mycompany.com", "builder name"))
```

Enjoy!

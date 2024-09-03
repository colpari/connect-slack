# Connect your Slack workspace with colpari Connect

* got to https://api.slack.com/apps/
* choose "Create New App"
  * choose "From a manifest"
  * select the Slack workspace you want to connect with colpari
  * paste the following into the JSON tab of the popup window:
  * ```
    {
        "display_information": {
            "name": "colpari Connect",
            "description": "Direct connection to your colpari team and services",
            "background_color": "#0095BA"
        },
        "features": {
            "bot_user": {
                "display_name": "colpari Connect",
                "always_online": false
            }
        },
        "oauth_config": {
            "scopes": {
                "user": [
                    "channels:history",
                    "channels:read",
                    "channels:write",
                    "channels:write.invites",
                    "channels:write.topic",
                    "chat:write",
                    "files:read",
                    "files:write",
                    "groups:history",
                    "identify",
                    "im:history",
                    "links:read",
                    "mpim:history"
                ],
                "bot": [
                    "channels:history",
                    "channels:join",
                    "channels:manage",
                    "channels:read",
                    "channels:write.invites",
                    "channels:write.topic",
                    "chat:write",
                    "files:read",
                    "files:write",
                    "groups:history",
                    "groups:read",
                    "im:history",
                    "incoming-webhook",
                    "links:read",
                    "mpim:history",
                    "team:read",
                    "users:read",
                    "users:write",
                    "groups:write",
                    "groups:write.invites",
                    "groups:write.topic",
                    "reactions:read"
                ]
            }
        },
        "settings": {
            "event_subscriptions": {
                "bot_events": [
                    "channel_history_changed",
                    "group_history_changed",
                    "im_history_changed",
                    "message.channels",
                    "message.groups",
                    "message.im",
                    "message.mpim",
                    "reaction_added",
                    "reaction_removed"
                ]
            },
            "interactivity": {
                "is_enabled": true
            },
            "org_deploy_enabled": false,
            "socket_mode_enabled": true,
            "token_rotation_enabled": false
        }
    }
    ```
  * click "Next", then "Create"
* create "App Level Token"
  * On the app main screen, under "Basic Information" -> "App-Level Tokens" click "Generate Token and Scopes"
  * name the token as you like (e.g. colpariConnect) and "Add Scope" `connection:write`, click "Generate"
  * copy the presented token (App Level Token) for submitting to us
* install app and create OAuth Tokens
  * On the app main screen, under "OAuth & Permissions" -> "OAuth Tokens" click "Install to workspace"
  * choose a channel to connect, click "Allow"
  * copy the presented "Bot User OAuth Token" for submitting to us
* Done! Now we need the following information from you:
  * "App Level Token" 
  * "Bot User OAuth Token"
  * channel name(s) to connect to colpari

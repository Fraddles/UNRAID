# Home-Assistant in Unraid

Running Home Assistant (container) in Unraid is not much different to running it on a regular Debian system when using the [Unraid Docker Compose plugin](https://forums.unraid.net/topic/114415-plugin-docker-compose-manager/).

Compared to my original [Debian setup](https://github.com/Fraddles/Home-Automation/tree/main/Home-Assistant), the only things that had to be changed were the;
* Name of th external network
* Host paths
* User and Group ID

I have also added GPU acceleration for Speech-to-Text transcoding using [wyoming-whisper](https://github.com/Fraddles/Home-Automation/tree/main/Voice-Assistant).  As a side note the Nvidia driver and docker runtime setup on Unraid is significantly simpler than a bare Linux due to the excellent [Nvidia driver plugin](https://forums.unraid.net/topic/98978-plugin-nvidia-driver/) that is available in the 'App store'.  However, it is still neccessary to map some extra libraries into the container for full CUDA support.

### Unraid Notifications in HA
We can use Unraids notification system with Home Assistant webhooks to get notifcations from Unraid into Home Assistant as Persistent Notifcations.

First we enable notifications for Agents in Unraid in Settings -> User preferences -> Notification Settings.  Check the 'Agents' box for the notifcation types you want to send to HA.
Scroll down and select an Agent to send the messages, I used the `ntfy.sh` one as it is pretty simple.
* Agent FUnction: Enabled
* Server URL: https://{home assistant URL}/api/webhook
* Token: {anything}
* Topic: {webhook_name}
* Title: {select one or more fields to use for the notifcation title}
* Message: {select one or more fields to use for the notifcation body}
* Click APPLY

In Home Assistant we need to setup a new automation with a webhook.
{TBC...}



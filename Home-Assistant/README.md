# Home-Assistant in Unraid

Running Home Assistant (container) in Unraid is not much different to running it on a regular Debian system when using the [Unraid Docker Compose plugin](https://forums.unraid.net/topic/114415-plugin-docker-compose-manager/).

Compared to my original [Debian setup](https://github.com/Fraddles/Home-Automation/tree/main/Home-Assistant), the only things that had to be changed were the;
* Name of th external network
* Host paths
* User and Group ID

I have also added GPU acceleration for Speech-to-Text transcoding using [wyoming-whisper](https://github.com/Fraddles/Home-Automation/tree/main/Voice-Assistant).  As a side note the Nvidia driver and docker runtime setup on Unraid is significantly simpler than a bare Linux due to the excellent [Nvidia driver plugin](https://forums.unraid.net/topic/98978-plugin-nvidia-driver/) that is available in the 'App store'.  However, it is still neccessary to map some extra libraries into the container for full CUDA support.

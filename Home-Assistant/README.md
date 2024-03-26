# Home-Assistant in Unraid

Running Home Assistant (container) in Unraid is not much different to running it on a regular Debian system when using the Unraid Docker Compose plugin.

Compared to my original [Debian setup](https://github.com/Fraddles/Home-Automation/tree/main/Home-Assistant), pretty much just the network name and host paths are different to accomodate Unraid, but I have also added GPU acceleration for Speech-to-Text transcoding using [wyoming-whisper](https://github.com/Fraddles/Home-Automation/tree/main/Voice-Assistant)

As a side note the Nvidia driver and docker runtime setup on Unraid is significantly simpler than a bare Linux due to the excellent [Nvidia driver plugin](https://forums.unraid.net/topic/98978-plugin-nvidia-driver/) that is available in the 'App store'.

However, it is still neccessary to map some extra libraries into the container for full CUDA support.

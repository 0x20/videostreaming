# Setup

You have two boxes. Both boxes are connected to the LAN with a network cable. Both boxes capture whatever is on their input and put it on the network as a multicast UDP stream.

 - The **Speaker box** has an HDMI input that receives the video from the camera and the audio of the mic.
 - The **Slides box** has a VGA input that is connected to the speaker's laptop and a VGA out that is connected to the beamer.

You need one computer that is connected to the same LAN as the two boxes. The computer captures the multicast UDP stream of both boxes, combines the streams into one and sends the combined stream to the internet. [OBS Studio](https://obsproject.com/) is software that can do this. OBS studio captures the stream of the speaker and the slides box, combines them into one, and sends that stream to the internet.

# Install OBS Studio on Ubuntu

Run the following commands in the terminal to install the latest version of OBS Studio on Ubuntu.

```bash
# Add the PPA repository so Ubuntu knows where to get OBS Studio
sudo add-apt-repository ppa:obsproject/obs-studio
# Get a list of the latest software from the repo's and install OBS Studio
sudo apt-get update && sudo apt-get install obs-studio
```

# Test the video stream

Install mpv

```bash
sudo apt install mpv
```

Look at the display.

![](img/display.jpg)

`stream` is the address of the unicast stream that the box puts on the LAN. Connect your laptop to the same LAN with a network cable and run the stream in mpv.

```bash
mpv udp://227.4.0.2:9000
```

# Capture streams in OBS

# Stream to the internet

# Tips

 - You will get the best video if the projector screen isn't visible in the video of the speaker. If the projector screen is in the video of the speaker, the camera will adjust it's brightness to the projector screen. This will cause the speaker to be very dark.
 - It is important that the video and audio of the speaker are captured by the same box so that the video and audio are synced. Otherwise, you will have a delay between the audio of the talk and the video of the speaker speaking which is very annoying.
 - If you don't have professional network equipment, it's best to put the streaming boxes on a separate LAN. Otherwise, they can overload your network.

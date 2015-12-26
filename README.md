# AdMute - Labeler
AdMute is an open-source project that foucuses on using data science in order to remove audio advertisments from audio streams.
## Structure of AdMute
AdMute is build up of the following components:
* The Labeler - used for labeling each time frame in the audio stream.
* The Preprocessor - used for extracting the most usable statistical features of the audio stream.
* The Trainer - used for training the learning algorithm to clasiffy each time frame in the audio stream.
* The Predictor - used for predicting the type of each time frame in the audio stream. This component is responsible for turning off the volume or changing the channel.

# AdMute - Labeler
The Labeler is the compnent that is used for creating labels for a sound stream.

# How to use?

### 1. Capture an audio stream

#### 1.1. Using GStreamer
First, you'll need to install gst:
```ssh
sudo add-apt-repository ppa:gstreamer-developers/ppa
sudo apt-get update
sudo apt-get install gstreamer1.0*
```
Then just play your favorite radio station and captrue it using:
```ssh
gst-launch-1.0 -v -m pulsesrc device="alsa_output.pci-0000_00_1b.0.analog-stereo.monitor" ! audioconvert ! vorbisenc ! oggmux ! filesink location="output.ogg"
```
That would capture the stream into output.ogg

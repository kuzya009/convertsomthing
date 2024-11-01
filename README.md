sudo apt-get update
sudo apt-get install -y gstreamer1.0-tools gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-ugly gstreamer1.0-alsa

gst-launch-1.0 --version

GST_DEBUG=3 gst-launch-1.0 filesrc location="2024-11-01T20:19:00.936Z.wav" ! decodebin ! autoaudiosink

sudo apt-get install -y ffmpeg

ffmpeg -i 2024-11-01T20:19:00.936Z.wav -ar 48000 -ac 2 2024-11-01T20:19:00.936Z_converted.wav
GST_DEBUG=3 gst-launch-1.0 filesrc location="2024-11-01T20:19:00.936Z_converted.wav" ! decodebin ! alsasink
pulseaudio --start

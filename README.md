rtl_fm_python
=============

An API and web application to interact with a running instance of RTL_FM

<img src="http://th0ma5w.github.io/rtl_fm_python.gif" alt="Screenshot" title="rtl_fm_python" /><br>
and with html5 audio player<br>
<img src="http://www.klug.gr/wp-content/uploads/2013/06/websdr.png" alt="Screenshot" title="rtl_fm_python_internet" />

# What

This is a Python library built upon the RTL-SDR project and allows you to use the 
RTL-SDR dongle to tune in arbitrary stations either with a simple web application
running on a built-in server, or programmatically with Python or any language using
the REST API provided.

- http://sdr.osmocom.org/trac/wiki/rtl-sdr
- http://www.reddit.com/r/rtlsdr

# Why

I wanted a minimalist remote control for demodulated audio coming from the usb stick
and something that could also provide that functionality on the Raspberry PI, or
allow for control of multiple dongles through web scripting, VPNs and internet.

# Features

- Based on the rtl_fm utility from the RTL-SDR Project https://github.com/steve-m/librtlsdr
- Drop in replacement for rtl_fm
- Live web interface based on React http://facebook.github.io/react/ and Flask http://flask.pocoo.org/
- RESTful API
- Change frequency, demodulation, and gain while running
- Read the RMS signal level
- Interact with rtl_fm with Python
- HTML5 audio player

# License

GPLv2

# How to Build

- Install the RTL-SDR software 
- Install Python dependencies for Flask

    sudo pip install flask

- Compile and link the modified rtm_fm source rtl_fm_python.c

    ./build.sh

If you have problems let me know. I may not be able to help as I'm not very experienced 
with building C applications.
- Change to your server ip in files web.sh and /static/index.html
- If your server is behind NAT open and forward tcp ports 10100 and 10101
- Install vlc

# Issues

- Can crash, probably
- Works best if started with WBFM modulation and sample rates if you're going to be switching around demodulation.
- May get out of sync with the features of rtl_fm due to my time and interest. Pull requests accepted!
- Audio may delay 15 seconds in streaming

# How to Run

## Web Interface & API

Included is a script called *web.sh* that shows an example usage. This script tunes to a
broadcast FM station and pipes the audio to vlc to transcode and stream.

By default the application should be running at http://127.0.0.1:10100/
and the audio stream (ogg) at http://127.0.0.1:10101/


# REST API
See
https://github.com/th0ma5w/rtl_fm_python


# Thanks

The rtl-sdr team and community for being awesome.
Th0ma5w, vlc




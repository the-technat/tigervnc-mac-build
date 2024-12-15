# tigervnc-mac-build

This repo contains a workflow that builds TigerVNC Viewer for MacOS with h.254 compression support.

## Background

I'm using a [PiKVM device with VNC](https://docs.pikvm.org/vnc/) for daily work. The PiKVM project recently added [h.254 support](https://github.com/TigerVNC/tigervnc/issues/1187) to TigerVNC. This makes TigeVNC among other tech details the best and most low-latency VNC client for use with PiKVM. Unfortunately they don't ship MacOS build with this feature enabled.

Thus I had to build / compile it myself. And since It was a bit tricky to figure out how to compile TigerVNC I thought I'll share the work I've done so far.
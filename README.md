# tigervnc-mac-build

This repo contains a workflow that builds TigerVNC Viewer for MacOS with h.254 compression support.

## Background

I'm using a [PiKVM device with VNC](https://docs.pikvm.org/vnc/) for daily work. The PiKVM project recently added [h.254 support](https://github.com/TigerVNC/tigervnc/issues/1187) to TigerVNC. This makes TigeVNC among other tech details the best and most low-latency VNC client for use with PiKVM. Unfortunately they don't ship a MacOS binary built with h.254 compression enabled.

Thus I had to build / compile it myself. And since It was a bit tricky to figure out how to compile TigerVNC I thought I'll share the work I've done so far.

## Get the build

You can find the binaries under the Releases tab. The version matches the one from TigerVNC.

### Runtime libraries

Currently the binaries aren't build with all libraries statically included. That means you need to install the libraries on your system as well for using my build: 

```console
brew install fltk@1.3 nettle ffmpeg gmp pixman gnutls
```

### Unsigned app

If you download one of my builds they are currently unsigned, which means you'll have to allow macOS to run them.

This is achieved by running this command against the `.app` file you have in your Applications folder:

```console
sudo xattr -cr "/Applications/TigerVNC Viewer x.y.z.app"
```
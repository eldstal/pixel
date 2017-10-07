# Pixel
Fast pixelflut server written in C. It is a collaborative coding game. Project the pixelflut-server onto a wall where many people can see it. You can set single pixel by sending a string like "PX [x] [y] [color]\n" "PX 100 300 00FF12\n". Use netcat, python or what ever you want.

## Hardware requirements

It works on a Raspberry Pi but it is no fun. Every x86 dual-core with a little bit of graphics power (for 2D SDL) should work. On an Core i3-4010U you can easily utilize 1 GBit Nic on --connections_max 1000. On large events 10 GBit fiber and a few more CPU-Cores are even more fun.

## Features
- Multithreaded
- Can display an overlay with some statistics
- Can fade out older pixels (do not activate this...)
- Serves real-time WebGL histogram and help text to browsers (same TCP port)

## Build SDL2 version (example)
On a clean Debian installation with "SSH server" and "standard system utilities":
```
apt update
apt install xorg git build-essential pkg-config libsdl2-dev -y
git clone https://github.com/larsmm/pixel.git
cd pixel
make sdl
./pixel_sdl --help
```

## Build Raspberry Pi version (not actively maintained)
```
apt update
apt install xorg git build-essential pkg-config libsdl2-dev -y
git clone https://github.com/larsmm/pixel.git
cd pixel
make pi
./pixel_sdl --help
```

## Stop Server
Press q

## TODO
- Use epoll() to check multiple sockets for I/O events at once
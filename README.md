# Selenoid Docker Containers
This repository contains [Docker](http://docker.com/) build files to be used for [Selenoid](http://github.com/aandryashin/selenoid) project. You can find prebuilt containers [here](https://hub.docker.com/u/selenoid/dashboard/).

## How containers are built

![layers](layers.png)

Each container consists of 3 or 4 layers:
1) **Base layer** - contains stuff needed in every container: Xvfb, fonts, cursor blinking fix, timezone definition and so on. This layer is always built manually.
2) **Optional Java layer** - contains latest Java Runtime Environment. Only needed for old Firefox versions incompatible with Geckodriver. This layer is always built manually.
3) **Browser layer** - contains browser binary. We create two versions: with APT cache and without it. The latter is then used to add driver layer.
4) **Driver layer** - container either respective web driver binary or corresponding Selenium server version.

Building procedure is automated with shell scripts ```selenium/build-dev.sh``` and ```selenium/build.sh``` that generate Dockerfile and then create browser and driver layers respectively. Before push each container is tested with these [tests](https://github.com/aerokube/selenoid-container-tests).

## Container information
### Firefox

| Container | Selenium version | Firefox version |
| --------------- | ---------------- | ---------------- |
| selenoid/firefox:3.6 | 2.20.0 | 3.6.16 i386 (dialogs may not work) |
| selenoid/firefox:4.0 | 2.20.0 | 4.0.1 i386 |
| selenoid/firefox:5.0 | 2.20.0 | 5.0.1 i386 |
| selenoid/firefox:6.0 | 2.20.0 | 6.0.2 i386 |
| selenoid/firefox:7.0 | 2.20.0 | 7.0.1 i386 |
| selenoid/firefox:8.0 | 2.20.0 | 8.0.1 i386 |
| selenoid/firefox:9.0 | 2.20.0 | 9.0.1 |
| selenoid/firefox:10.0 | 2.32.0 | 10.0.2 |
| selenoid/firefox:11.0 | 2.32.0 | 11.0 |
| selenoid/firefox:12.0 | 2.32.0 | 12.0 |
| selenoid/firefox:13.0 | 2.32.0 | 13.0 |
| selenoid/firefox:14.0 | 2.32.0 | 14.0.1 |
| selenoid/firefox:15.0 | 2.32.0 | 15.0.1 |
| selenoid/firefox:16.0 | 2.32.0 | 16.0.2 |
| selenoid/firefox:17.0 | 2.32.0 | 17.0.1 |
| selenoid/firefox:18.0 | 2.32.0 | 18.0.2 |
| selenoid/firefox:19.0 | 2.32.0 | 19.0.2 |
| selenoid/firefox:20.0 | 2.32.0 | 20.0 |
| selenoid/firefox:21.0 | 2.32.0 | 21.0 |
| selenoid/firefox:22.0 | 2.32.0 | 22.0 |
| selenoid/firefox:23.0 | 2.35.0 | 23.0.1 |
| selenoid/firefox:24.0 | 2.39.0 | 24.0 |
| selenoid/firefox:25.0 | 2.39.0 | 25.0.1 |
| selenoid/firefox:26.0 | 2.39.0 | 26.0 |
| selenoid/firefox:27.0 | 2.40.0 | 27.0.1 |
| selenoid/firefox:28.0 | 2.41.0 | 28.0 |
| selenoid/firefox:29.0 | 2.43.1 | 29.0.1 |
| selenoid/firefox:30.0 | 2.43.1 | 30.0 |
| selenoid/firefox:31.0 | 2.44.0 | 31.0 |
| selenoid/firefox:32.0 | 2.44.0 | 32.0.3 |
| selenoid/firefox:33.0 | 2.44.0 | 33.0.3 |
| selenoid/firefox:34.0 | 2.45.0 | 34.0.5 |
| selenoid/firefox:35.0 | 2.45.0 | 35.0.1 |
| selenoid/firefox:36.0 | 2.45.0 | 36.0.1 |
| selenoid/firefox:37.0 | 2.45.0 | 37.0.2 |
| selenoid/firefox:38.0 | 2.45.0 | 38.0.5 |
| selenoid/firefox:39.0 | 2.45.0 | 39.0.3 |
| selenoid/firefox:40.0 | 2.45.0 | 40.0.3 |
| selenoid/firefox:41.0 | 2.45.0 | 41.0.2 |
| selenoid/firefox:42.0 | 2.47.1 | 42.0 |
| selenoid/firefox:43.0 | 2.47.1 | 43.0.4 |
| selenoid/firefox:44.0 | 2.53.1 | 44.0.2 |
| selenoid/firefox:45.0 | 2.53.1 | 45.0.2 |
| selenoid/firefox:46.0 | 2.53.1 | 46.0.1 |
| selenoid/firefox:47.0 | 2.53.1 | 47.0.1 |
| selenoid/firefox:48.0 | 3.2.0 + GD 0.13.0 | 48.0.2 (native events and proxies don't work) |
| selenoid/firefox:49.0 | 3.2.0 + GD 0.13.0 | 49.0.2 (native events and switching between windows don't work) |
| selenoid/firefox:50.0 | 3.2.0 + GD 0.13.0 | 50.0.2 (native events, switching windows and proxies don't work) |
| selenoid/firefox:51.0 | 3.2.0 + GD 0.14.0 | 51.0.1 (native events, switching windows and proxies don't work) |
| selenoid/firefox:52.0 | 3.3.1 + GD 0.15.0 | 52.0.2 (native events, switching windows don't work; proxy capability format could change) |

### Chrome

| Container | Chromedriver version |
| --------- | -------------------- |
| selenoid/chrome:29.0 | 2.6 |
| selenoid/chrome:30.0 | 2.8 |
| selenoid/chrome:31.0 | 2.9 |
| selenoid/chrome:32.0 | 2.9 |
| selenoid/chrome:33.0 | 2.10 |
| selenoid/chrome:34.0 | 2.10 |
| selenoid/chrome:35.0 | 2.10 |
| selenoid/chrome:36.0 | 2.12 |
| selenoid/chrome:37.0 | 2.12 |
| selenoid/chrome:38.0 | 2.13 |
| selenoid/chrome:39.0 | 2.14 |
| selenoid/chrome:40.0 | 2.15 |
| selenoid/chrome:41.0 | 2.15 |
| selenoid/chrome:42.0 | 2.16 |
| selenoid/chrome:43.0 | 2.20 |
| selenoid/chrome:44.0 | 2.20 |
| selenoid/chrome:45.0 | 2.20 |
| selenoid/chrome:46.0 | 2.21 |
| selenoid/chrome:47.0 | 2.21 |
| selenoid/chrome:48.0 | 2.21 |
| selenoid/chrome:49.0 | 2.22 |
| selenoid/chrome:50.0 | 2.22 |
| selenoid/chrome:51.0 | 2.23 |
| selenoid/chrome:52.0 | 2.24 |
| selenoid/chrome:53.0 | 2.26 |
| selenoid/chrome:54.0 | 2.27 |
| selenoid/chrome:55.0 | 2.28 |
| selenoid/chrome:56.0 | 2.28 |
| selenoid/chrome:57.0 | 2.28 |

### Opera

| Container | Selenium version |
| --------- | ---------------- |
| selenoid/opera:12.16 | 2.35.0 |

| Container | Operadriver version |
| --------- | ------------------- |
| selenoid/opera:15.0 | 0.2.2 |
| selenoid/opera:16.0 | 0.2.2 |
| selenoid/opera:17.0 | 0.2.2 |
| selenoid/opera:18.0 | 0.2.2 |
| selenoid/opera:19.0 | 0.2.2 |
| selenoid/opera:20.0 | 0.2.2 |
| selenoid/opera:21.0 | 0.2.2 |
| selenoid/opera:22.0 | 0.2.2 |
| selenoid/opera:23.0 | 0.2.2 |
| selenoid/opera:24.0 | 0.2.2 |
| selenoid/opera:25.0 | 0.2.2 |
| selenoid/opera:26.0 | 0.2.2 |
| selenoid/opera:27.0 | 0.2.2 |
| selenoid/opera:28.0 | 0.2.2 |
| selenoid/opera:29.0 | 0.2.2 |
| selenoid/opera:30.0 | 0.2.2 |
| selenoid/opera:32.0 | 0.2.2 |
| selenoid/opera:33.0 | 0.2.2 |
| selenoid/opera:34.0 | 0.2.2 |
| selenoid/opera:35.0 | 0.2.2 |
| selenoid/opera:36.0 | 0.2.2 |
| selenoid/opera:37.0 | 0.2.2 |
| selenoid/opera:38.0 | 0.2.2 |
| selenoid/opera:39.0 | 0.2.2 |
| selenoid/opera:40.0 | 0.2.2 |
| selenoid/opera:41.0 | 0.2.2 |
| selenoid/opera:42.0 | 0.2.2 |
| selenoid/opera:43.0 | 0.2.2 |
| selenoid/opera:44.0 | 0.2.2 |

---
title: "Cameras using MotionEyeOS"
date: 2022-03-08T22:35:03-04:00
tags: ['home-lab']
---

{{< context >}}

## Open-source home camera system

The MotionEyeOS camera project was mostly a project of "what's possible?" I took a couple of Raspberry Pi and deployed new software, turning them into a combination of a camera server and multiple wireless cameras. Being able to self-host software that was being sold commerically was really cool, because it meant that "my data" would stay "my data."

This project also proved that self-hosting didn't have to mean a loss of features -- I had multiple cameras set up around the house, communicating wirelessly, live streaming video in decent quality, with the ability to do video capture when they sensed motion. This project was a demonstration that I didn't have to trust some faceless corporation with my camera data, I could do it myself using free and open-source software (FOSS).


As I found out in 2023 when attempting to install MotionEyeOS into a Docker container, there are no images for MotionEyeOS that work on the x86 platform. Therefore, I was unable to test out the software again, as I did not have an interest in reinstalling the OS onto a Raspberry Pi.

---

## The Build

### Hardware stack:

- Raspberry Pi 4, 8GB (server)
- Raspberry Pi 4, 8GB (camera)
- Raspberry Pi Zero W (camera)

I remember having one issue with the web UI related to adding cameras. I think the issue was not including `http://` in front of the camera's IP address.

![MotionEye - Add Camera](/images/motioneye-add-camera.png)

*The issue -was- not including "http://" in front of the camera IP addresses. Image from [MotionEye GitHub](https://github.com/motioneye-project/motioneye/wiki/Screenshots).*

---

## Fresh Install Bullet Points

Here’s how I would rebuild my camera system if I needed to:

- Follow the [MotionEyeOS documentation](https://github.com/motioneye-project/motioneyeos/wiki/Installation) to set up the server
- Then, use the same documentation to set up the cameras

Thanks to those who got me here!

- Tom from Lawrence Systems on Youtube for [verification re adding cameras](https://www.youtube.com/watch?v=og-zI0CozLs&t=730s).

## {{< youtube id="og-zI0CozLs?start=730" title="Raspberry Pi Motion Detection Surveillance Camera System using MotionEyeOS" >}}


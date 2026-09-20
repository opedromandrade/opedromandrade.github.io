+++
date = '2026-09-20T22:39:05+01:00'
draft = false
title = 'Nfo Forge'
+++
{{< figure src="/img/nfoforge.jpg" alt="nfoforge" width="640" >}}

This weekend I've been reviewing some code for the scripts I built to easily create a [.nfo](https://en.wikipedia.org/wiki/.nfo) file for MP3-encoded albums 🎵

One variant uses [ffmpeg](https://ffmpeg.org/) and [ffprobe](https://ffmpeg.org/ffprobe.html) to gather all the metadata. Sadly, this approach falls short when you need to know the specific encoding settings used during the actual rip. Unfortunately, that detail just isn't available to read with [ffprobe](https://ffmpeg.org/ffprobe.html) 😕

So I created another script using a tool that's not quite open-source—but  - still very cool— called [mp3guessenc](https://mp3guessenc.sourceforge.io/). This little gem provided exactly the information I was looking to output 🎯

It initially used [ffprobe](https://ffmpeg.org/ffprobe.html) to get some of its information, but it wasn't necessary and now all is made *in house* so to speak.

Taming it, however, was no small feat. Parsing ID3v2.3 tags and handling UTF-8 characters required some serious digging and patience. But after a bit of elbow grease, I finally got it working smoothly!

[Here](https://github.com/opedromandrade/nfo-forge/tree/main/examples) are some example [.nfo](https://en.wikipedia.org/wiki/.nfo) files if you choose  to take a peek at: [nfo-forge examples](https://github.com/opedromandrade/nfo-forge/tree/main/examples)

If you compare them, they might look identical at first glance, but notice the difference: the one generated via [ffprobe](https://ffmpeg.org/ffprobe.html) lacks those crucial encoding settings.

As usual, I've bundled all necessary modules together with the scripts to make them plug-and-play ready 📦

As always if you have any ideas or plan to contribute, feel free to do so! 🛠️
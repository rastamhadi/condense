# condense
My personal collection of Rake tasks for generating condensed audio from YouTube videos for [passive immersion](https://refold.la/roadmap/stage-0/c/passive-listening) in Korean.

## Prerequisites

```console
$ brew install ffmpeg youtube-dl
$ pip3 install subs2cia
```

## Usage

```console
# e.g. for the video https://www.youtube.com/watch?v=PN7rJrGo9a0
# bundle exec rake PN7rJrGo9a0.condensed.mp3
$ bundle exec rake YOUTUBE_VIDEO_ID.condensed.mp3
```

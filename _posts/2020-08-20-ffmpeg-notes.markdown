---
layout: post
title:  "FFmpeg命令行小笔记"
date:   2020-08-20 15:42:00 +0800
categories: chinese
---

FFmpeg是处理音视频常用的开源软件。

## 命令行组件
- ffmpeg：用于对视频文档或音频档案转换格式
- ffplay：一个简单的播放器
- ffprobe：用于显示媒体文件的信息

## 常用参数
- `-i`：设置输入文件名。
- `-f`：设置输出格式。
- `-y`：若输出文件已存在时则覆盖文件。
- `-t`：指定输出文件的持续时间，以秒为单位。
- `-ss`：从指定时间开始转换，以秒为单位。
- `-c`：指定输出文件的编码。
- `-vcodec(-c:v)`：设置影像影像编解码器，未设置时则使用与输入文件相同之编解码器。
- `-acodec(-c:a)`：设置声音编解码器，未设置时与影像相同，使用与输入文件相同之编解码器。

## 常用命令

### 常见缩写
    vf = filter:v
    af = filter:a

### 调整大小
    ffmpeg -i in.mp4 -vf scale=-1:256 -c:a copy out.mp4
	ffmpeg -i in.png -vf scale=256:256 out.png

### 画面裁切
	ffmpeg -i in.mp4 -vf "crop=256:256:64:0" -c:a copy out.mp4

### 视频三倍速
	ffmpeg -i in.mp4 -vf setpts=PTS/3 out.mp4

### 裁剪音频片段
	ffmpeg -ss 00:01:05.500 -to 00:01:34 -i in.mp3 -acodec copy out.mp3
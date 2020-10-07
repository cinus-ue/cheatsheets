# FFMPEG CHEAT SHEET

## SWITCHING CONTAINERS
```
ffmpeg -i file.mp4 file.avi
ffmpeg -i file.mkv -acodec copy -vcodec copy file.mp4
```

## TRIMMING
```
Without re-encoding:
ffmpeg -ss [start] -i in.mp4 -t [duration] -c copy out.mp4

-ss   specifies the start time, e.g. 00:01:23.000 or 83 (in seconds)
-t    specifies the duration of the clip (same format).
Recent ffmpeg also has a flag to supply the end time with -to.
-c    copy copies the first video, audio, and subtitle bitstream from the input to the output file without re-encoding them. This won't harm the quality and make the command run within seconds.

With re-encoding:
ffmpeg -ss [start] -i in.mp4 -t [duration] -c:v libx264 -c:a aac -strict experimental -b:a 128k out.mp4

ffmpeg -i <input> -ss 00:01:45 -t 00:02:35 -vcodec copy -acodec copy <output>
ffmpeg -i <input> -vcodec copy -acodec copy -ss 00:00:00 -to 00:10:00 <input> -y
```

## EXTRACTING AUDIO STREAM
```
ffmpeg -i file.mp4 -vn -acodec copy output.aac 
```

## CREATING THUMBNAILS
```
ffmpeg -i <input file> -vf fps=1/60 thumbnails/thumb%03d.png
```

## SPLIT VIDEO TO IMAGES
```
ffmpeg -i video.mp4 image%d.jpg
```

## CROPPING
```
ffmpeg -i <input> -filter:v "crop=640:480:100:25" <output>
```

## SCALING
```
ffmpeg -i <input> -vf scale=640:480 <output>
```

## JOIN .ts FILES
```
ffmpeg copy /b segment1_0_av.ts+segment2_0_av.ts+segment3_0_av.ts full.ts
```

## WATERMARK
```
ffmpeg -i in.mp4 -i watermark.png -filter_complex "overlay=36:36" -codec:a copy out.mp4
```

## STREAMING
```
ffmpeg -re -i ./1080P.264 -vcodec copy -f rtp rtp://127.0.0.1:80>rtp_h264.sdp

ffplay -protocol_whitelist "file,udp,rtp" -i rtp_h264.sdp

ffmpeg  -re -i <media_file> -an -vcodec copy -f rtp rtp://<IP>:5001 -vn -acodec copy -f rtp rtp://<IP>:5003 > media.sdp
```

## SDP
```
v=0
o=- 0 0 IN IP4 127.0.0.1
s=No Name
c=IN IP4 127.0.0.1
t=0 0
a=tool:libavformat 56.15.102
m=video 1234 RTP/AVP 96
a=rtpmap:96 H264/90000
```
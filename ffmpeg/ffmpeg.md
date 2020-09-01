# FFMPEG CHEAT SHEET

```
ffmpeg -i ./in.mp4 -vcodec copy -acodec copy -ss 00:00:00 -to 00:10:00 ./out.mp4 -y
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
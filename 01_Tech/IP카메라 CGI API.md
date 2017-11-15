# IP카메라 CGI API

[TOC]

## 1. 요청방식
1. HTTP GET
2. Parameters
  * http://[URL]/cgi_bin/[cgi]?auth_64=[account info]&category=[category]&[key=value]
3. cgi
  1. setup_get.cgi
  2. setup_cmd.cgi
4. account info
  1. [id:password] => base64 encoding
5. category
  1. video_stream

## 2. setup_get.cgi : 설정값 얻어오기
### 2.1 video_stream
1. Request
  * http://[URL]/cgi_bin/setup_get.cgi?auth_64=[account info]&**category=video_stream**
2. Response

```
onoff_0=1
codec_0=0
resol_0=HD1080
fps_0=30
qty_0=1
max_bitrate_0=5000
gop_0=30
audio_0=1
Iref_0=0
title_0=MAIN STREAM
onoff_1=1
codec_1=0
resol_1=VGA
fps_1=30
qty_1=1
max_bitrate_1=750
gop_1=30
audio_1=1
Iref_1=0
title_1=SUB STREAM
encryption=0
```

## 3. setup_cmd.cgi : 설정값 적용하기
### 3.1 video_stream
1. Request
  * http://[URL]/cgi_bin/setup_cmd.cgi?auth_64=[account info]&**category=video_stream&encryption=1**

2. Response

   ```
   HTTP/1.1 200 OK
   ```


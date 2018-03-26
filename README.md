# livego
直播服务器
简单高效的直播服务器：
- 安装和使用非常简单；
- 纯 Golang 编写，性能高，跨平台；
- 支持常用的传输协议、文件格式、编码格式；

#### 支持的传输协议
- [x] RTMP  适合延迟比较小3-4s
- [x] AMF
- [x] HLS   延迟一般在10s
- [x] HTTP-FLV 延迟一般在10s

#### 支持的容器格式
- [x] FLV  支持flash格式
- [x] TS

#### 支持的编码格式
- [x] H264
- [x] AAC
- [x] MP3

#### 从源码编译
1. 下载源码 `git clone https://github.com/zhangjunfang/livego.git`
2. 去 livego 目录中 执行 `go build`

## 使用
2. 启动服务：执行 `livego` 二进制文件启动 livego 服务；
3. 上行推流：通过 `RTMP` 协议把视频流推送到 `rtmp://localhost:1935/live/movie`，例如使用 `ffmpeg -re -i demo.flv -c copy -f flv rtmp://localhost:1935/live/movie` 推送；
4. 下行播放：支持以下三种播放协议，播放地址如下：
    - `RTMP`:`rtmp://localhost:1935/live/movie`
    - `FLV`:`http://127.0.0.1:7001/live/movie.flv`
    - `HLS`:`http://127.0.0.1:7002/live/movie.m3u8`

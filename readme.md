## ffmpeg 轉檔指令

```shell

ffmpeg -i ./src/songs/song.mp3 -c:a libmp3lame -b:a 128k -map 0:0 -f segment -segment_time 10 -segment_list ./dist/music/song/song.m3u8 -segment_format mpegts ./dist/music/song/song%03d.ts

ffmpeg -i ./src/songs/shin.mp3 -c:a libmp3lame -b:a 128k -map 0:0 -f segment -segment_time 10 -segment_list ./dist/music/shin/shin.m3u8 -segment_format mpegts ./dist/music/shin/shin%03d.ts

```

## player

1. [HTML5 video tag (only for Edge)](index.html)
1. [flowPlayer.js](index2.html)
1. [Clappr Player](index3.html)
1. [HLS.js](index4.html)


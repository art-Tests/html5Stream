# Intro

將檔案透過 ffmpeg 切割成小檔案，利用網頁 player 播放串流使用，此為 POC 專案，此專案僅負責透過網頁撥放 mp3 切割成小檔案的 m3u8 清單

先透過 ffmpeg 將兩個音樂檔案轉檔好，放到固定的位置，本專案中設定為

1. `/dist/music/shin`
1. `/dist/music/song`

> 測試開發可透過 VSCode 套件 [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)建立測試網站

## ffmpeg 轉檔指令

```shell

ffmpeg -i ./src/songs/song.mp3 -c:a libmp3lame -b:a 128k -map 0:0 -f segment -segment_time 10 -segment_list ./dist/music/song/song.m3u8 -segment_format mpegts ./dist/music/song/song%03d.ts

ffmpeg -i ./src/songs/shin.mp3 -c:a libmp3lame -b:a 128k -map 0:0 -f segment -segment_time 10 -segment_list ./dist/music/shin/shin.m3u8 -segment_format mpegts ./dist/music/shin/shin%03d.ts

```

## player

1. [HTML5 video tag (only for Edge)](src/index.html)
1. [flowPlayer.js](src/index2.html)
1. [Clappr Player](src/index3.html)
1. [HLS.js](src/index4.html)

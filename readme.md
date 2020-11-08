# Тестирование обработки видео

Удалить все аудио дорожки 

original-4k.mp4 => muted-4k.mp4

223 мб => 222.4 мб
```shell script
ffmpeg -i original-4k.mp4 -vcodec copy -an muted-4k.mp4
```

Конвертировать в WebM

muted-4k.mp4 => muted-4k.webm

222.4 мб => 14.8 мб
```shell script
ffmpeg -i muted-4k.mp4 -c:v libvpx-vp9 -crf 30 -b:v 0 -b:a 128k -c:a libopus muted-4k.webm
```

Удалить все аудио дорожки 

original-fullhd.mp4 => muted-fullhd.mp4

29.3 мб => 29.2 мб
```shell script
ffmpeg -i original-fullhd.mp4 -vcodec copy -an muted-fullhd.mp4
```

Конвертировать в WebM 

muted-fullhd.mp4 => muted-fullhd.webm

29.2 мб => 1.8 мб
```shell script
ffmpeg -i muted-fullhd.mp4 -c:v libvpx-vp9 -crf 30 -b:v 0 -b:a 128k -c:a libopus muted-fullhd.webm
```

### Safary 12.1-13.1 - Safari only supports VP8 used in WebRTC

### Safari only supports VP8 used in WebRTC and VP9 used in WebRTC

Конвертировать в WebM Codec VP8

muted-fullhd.mp4 => muted-fullhd-vp8.webm

29.2 мб => 1.6 мб
```shell script
ffmpeg -i muted-fullhd.mp4 -vcodec libvpx -qmin 0 -qmax 50 -crf 10 -b:v 1M -acodec libvorbis muted-fullhd-vp8.webm
```

muted-4k.mp4 => muted-4k-vp8.webm

222.4 мб => 6.5 мб
```shell script
ffmpeg -i muted-4k.mp4 -vcodec libvpx -qmin 0 -qmax 50 -crf 10 -b:v 1M -acodec libvorbis muted-4k-vp8.webm
```

Конвертировать в WebM Codec VP9

muted-fullhd.mp4 => muted-fullhd-vp9.webm

29.2 мб => 1.6 мб
```shell script
ffmpeg -i muted-fullhd.mp4 -vcodec libvpx -qmin 0 -qmax 50 -crf 10 -b:v 1M -acodec libvorbis muted-fullhd-vp9.webm
```

29.2 мб => 1.6 мб
```shell script
ffmpeg -i muted-fullhd.mp4 -vcodec libvpx -qmin 0 -qmax 50 -crf 1 -b:v 1M -acodec libvorbis muted-fullhd-vp9.webm
```

## Источники информации
https://gist.github.com/Vestride/278e13915894821e1d6f

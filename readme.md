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

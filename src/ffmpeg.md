# FFmpeg

Super cheat sheet for ffmpeg

Sauce : https://gist.github.com/steven2358/ba153c642fe2bb1e47485962df07c730
https://engineering.giphy.com/how-to-make-gifs-with-ffmpeg/

### Convert mp4 to gif

```shell
ffmpeg -i generated_2.mp4 -vf "flags=lanczos,split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" -loop 0 ben.gif
```

### Trim

use **-ss** to seek and **-t** to set time

```shell
ffmpeg -i in.mp4 -ss 1:00 -t 0:05 out.mp4
```

### Extract frames

```shell
ffmpeg -i pfp.mp4  -vf "fps=10" frames/%03d.png
```

### Make gif

```shell
ffmpeg -i frames/%03d.png -vf "setpts=2*PTS" out.gif
```

### Make gif

generate palette

```shell
ffmpeg -i frames/%03d.png -vf "palettegen" pallete.png
```

```shell
ffmpeg -i frames/%03d.png -i pallete.png -filter_complex "paletteuse" out.gif
```

# FFmpeg

Super cheat sheet for ffmpeg

Sauce : https://gist.github.com/steven2358/ba153c642fe2bb1e47485962df07c730

### Convert mp4 to gif

```shell
ffmpeg -i generated_2.mp4 -vf "flags=lanczos,split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" -loop 0 ben.gif
```

### Trip

use **-ss** to seek and **-t** to set time
```shell
ffmpeg -i in.mp4 -ss 1:00 -t 0:05 out.mp4
```
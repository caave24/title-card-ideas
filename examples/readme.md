# convert all mp4 to gifs
- for f in *.mp4; do
-     ffmpeg -i "$f" \
-     -vf "fps=15,scale=800:-1:flags=lanczos,split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" \
-     "${f%.mp4}.gif"
- done

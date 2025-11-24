### convert wav to mp3

    ffmpeg -i inputfile.wav -ab 320k outputfile.mp3

### convert mov to mp4 (compress to reduce file size)

    ffmpeg -i input.mov -c:v libx264 -crf 23 -preset medium -c:a aac -b:a 128k output.mp4

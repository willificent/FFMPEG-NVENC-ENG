videoconvert is a BASH script for converting large video files with lots of extra "junk" to a smaller file size with only the original language audio, and any English audio and subtitles. (Discards everything else)<br>
Inputs: any mkv,mp4,mov,avi,ts,m4v,or webm in the current folder <br>
Video format: h265, 1920 max width (maintains aspect ratio)
Audio streams: Keeps audio stream 0 (first one), and any other audio streams in English.
Audio format: Converts multistream audio to 384kbps DD5.1; stereo/mono to 192kbps

Output: mkv, 1080p

Installation: 
   -Install the script: /usr/local/bin/{yourfilename}
   -chmod +x /usr/local/bin/{yourfilename}

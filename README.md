videoconvert is a BASH script for converting large video files with lots of extra "junk" to a compact 1GB/hour x265 video stream with only the original language audio in DD5.1 or stereo, any additional English audio streams, and English subtitles. (Discards everything else) This script is GPU accelerated for encode, decode, and scale using the available Nvidia libraries in the nvidia-driver and associated packages.<br><br>
Dependencies: ffmpeg, nvidia-driver, nvenc, nvdec (sudo apt install...)<br>
<ul><li>Inputs: any mkv,mp4,mov,avi,ts,m4v,or webm in the current folder</li>
<li>Video format: h265, 1920 max width (maintains aspect ratio)</li>
<li>Audio streams: Keeps audio stream 0 (first one), and any other audio streams in English.</li>
<li>Audio format: Converts multistream audio to 384kbps DD5.1; stereo/mono to 192kbps</li>
<li>Output: mkv, 1080p</li></ul>
Installation: 
<ul><li>Install the script: /usr/local/bin/{yourfilename}</li>
<li>chmod +x /usr/local/bin/{yourfilename}</li></ul>

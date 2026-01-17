<b>videoconvert</b> is a BASH script for converting large video files with lots of extra "junk" to a compact 1GB/hour x265 video stream with only the original language audio in DD5.1 or stereo, any additional English audio streams, and English subtitles. (Discards everything else) This script is GPU accelerated for encode, decode, and scale using the available Nvidia libraries in the nvidia-driver and associated packages.<br><br>
Dependencies: ffmpeg, nvidia-driver, nvenc, nvdec (sudo apt install...)<br>
<br>Compatibility check:
<br><br>Does ffmpeg have access to the encoders? 
<br>ffmpeg -hide_banner -encoders | grep -E 'hevc_nvenc'
<br><br>Does ffmpeg support CUDA scaling?
<br>ffmpeg -hide_banner -filters | grep -E 'scale_cuda|hwupload_cuda'
<ul><li>Inputs: all mkv,mp4,mov,avi,ts,m4v,or webm in the specified or current folder</li>
<li>Video format: h265 via NVENC, 1920 max width (maintains aspect ratio)</li>
<li>Audio stream handling: Keeps audio stream 0 (first one), and any other audio streams in English.</li>
<li>Audio format: Converts multistream audio to 384kbps DD5.1; stereo/mono to 192kbps</li>
<li>Subtitle handling: Keeps all English language subtitles, discards the rest</li></ul>
Output: 
  <ul><li>File type: mkv
  <li>{original_file_name}.1080p.hevc_nvenc.w1920.mkv</li></li></ul>
<b>Installation:</b>
<br>git clone …
<br>sudo install -m 755 videoconvert /usr/local/bin/videoconvert
<br>cd /path/to/movies && videoconvert

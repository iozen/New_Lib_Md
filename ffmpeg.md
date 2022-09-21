
ffmpeg -ss 00:00:03 -to 00:00:08 -i movie.mp4 cut.mp4 


**720p**

ffmpeg -ss 00:00:03 -to 00:00:08  -s hd720 -i movie.mp4 cut.mp4

ffmpeg -i input.mp4 -vf scale=$w:$h <encoding-parameters> output.mp4


### 2 video to one 


ffmpeg -i input1.mp4 -i input2.wmv -filter_complex "[0:0][0:1][1:0][1:1]concat=n=2:v=1:a=1[outv][outa]" -map "[outv]" -map "[outa]" output.mp4


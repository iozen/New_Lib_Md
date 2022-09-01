
ffmpeg -ss 00:00:03 -to 00:00:08 -i movie.mp4 cut.mp4 


**720p**

ffmpeg -ss 00:00:03 -to 00:00:08  -s hd720 -i movie.mp4 cut.mp4

ffmpeg -i input.mp4 -vf scale=$w:$h <encoding-parameters> output.mp4


### 2 video to one 


ffmpeg -i movie.mp4 -i movie2.mp4  result.mp4 


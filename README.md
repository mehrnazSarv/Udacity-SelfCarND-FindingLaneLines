Finding Lane Lines on the Road
The goals / steps of this project are the following:
Make a pipeline that finds lane lines on the road Reflect on your work in a written report
1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.
My pipeline to find the lane lines on the road include 6 steps.
1. Inthefirststep,Ihaveusedthecv2.cvtColorfunctiontoseetheimageas
grayscale.
2. Inthisstep,thereturnedimagefromstep1hasusedthecv2.GaussianBlur
function to reduce noise with kernel size of 5.
3. Whentheimagehasbeensmoothedfrompreviousstep,Ihaveusedthe
cv2.Canny method with low threshold of 50 and 150 for high thresholds.
4. Inthisstep,Ihaveusedtheregion_of_interestfunctiontoreturnamaskfor
limiting of interest region.
5. Next,byapplyingthecv2.HoughLinesmethod,Icouldreturnthehoughlines
drawn.
6. Inthelaststep,thefindinglanelinescanbedetectedbyusingcv2.addWrighted
method.
In order to explain of draw_lines() function, I have determined each line is in left side or right side. A positive slope denotes that a line segment is in the left side, though a negative slope shows that a line segment is in the right side.
Left lane line segments that the slope is more than 0.4 (or less than -0.4 for the right lane) are acceptable. Then the average of selected line segments will be calculated. Finally, the line segment has been extended to the whole of graph.
2. Identify potential shortcomings with your current pipeline
As a potential shortcoming for me is how I can determine the interest region of an image. And also, how can I examine each line that returned by hough function.
3. Suggest possible improvements to your pipeline
One improvement could be to how can use knowledge gained from the previous frame to recognize future frames.

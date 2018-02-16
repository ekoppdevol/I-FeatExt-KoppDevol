Eli Kopp-Devol

Goals:
  -Use face tracker to control basic mini game
  -Use weki input helper to control game using both y/z velocity and a smoothed x position

Tools:
  -VideoInput_FaceDetection_Processing_3Inputs for the input: while I intended on using a Kinect for this assignment, it disapeared from      the classroom I left it in on the day I was to do the assignment so this was the next best thing.
  -Processing_GameExample_1DTW for the output: I modified this sketch slightly so that it accepts 2 different classifier inputs rather        than one DTW input.

Outcome:
  -Using the tools listed above I was able to control the mini game using only head gestures. I used weki input helper to average the x position values which in turn controlled the left/right movement of the block. The averaging may have not been nececery here but it helped eliminate any weird noise from the webcam input so that the control was very precise. Holding your head to the left caused the block to move left and holding your head to the right caused the block to move right. I then used weki input helper to calculate the velocity of head movement in the y and z directions. I then trained wekinator to recognize a rapid head nod and used this gesture to cause the small block to jump. Putting this all togeather allowed the user to move the block left and right by shifting their head in the appropriate direction and make the block jump with a quick nod. Unfortunately the game sketch seemed to have a hard time processing both commands and the same time so technical game play was quite challenging. 
  
ML Algorithm:
  -Because the first input of simple head x position to control the left/right motion of the block was relatively simple, all of the tested algorithms gave a 100% fit except the decision tree (and boosting on a decision tree) which gave a slight reduction to only 99.37% accuracy. 
  -For the output of the head nod, I found that boosing on a decision tree gave the most reliable classification as well as the best fit to the data with a fit of 80.51% with an unboosted decision tree coming in close second with a fit of 79.42%. Testing on KNN with one neighbor also gave a decent fit (79%) but seemed to be lest reliable in application. Testing on KNN with 5 neighbors, a boosted decision stump and naive bayes gave 77.62%, 77.62% and 78.7% accuracy respectively. 
 

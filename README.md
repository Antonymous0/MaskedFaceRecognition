# MaskedFaceRecognition

![image](https://user-images.githubusercontent.com/77621697/180694140-8d2bd4bc-03f3-4e2c-87c1-0d613e518dd1.png)

The above image shows the flowchart of how the model works.

The attached code verifies the masked and unmasked images of a person and returns true if they are the same person else false. The model works in the following way:
  1. Detect unmasked face of an individual and superimpose the lower part of a stock image onto the lower part of the unmasked face.
  2. Superimpose the lower part of stock image onto the masked part of the masked image by detecting the mask.
  3. Use the verify function of deepface with a certain threshold value to determine whether the 2 images (the masked and unmasked images) were of the same person or not.

Shortcomings of the model:
  1. The mask detection model is undertrained (using around 3000 training examples) while the face detection model is deepface which is state-of-the-art.
  2. As a result of the above, the model doesn't work well for tilted images.
  
Ways to enhance model performance:
  1. Tuning the threshold values using algorithms like gradient descent.
  2. Using multiple models from deepface and taking average of the distances.
  3. Instead of forced superposition of a constant image we can detect the facial features and superimpose accordingly.
  4. Use multiple lower half stock images.
  5. Improve mask detection algorithm as it is undertrained.

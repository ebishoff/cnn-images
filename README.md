# cnn-images
Convolutional Neural Network for flower dataset

# Introduction
Our overarching question is how well can we classify images of flowers based off a snapshot of them? Someday could we create an app that allows us to tell you the type of flower you are seeing based off just the image? Another focus of this project was to have a better understanding of Convolutional Neural Networks (CNN). Convolutional Neural Networks are known for working well with image classification. The CNN can take in a h×w×3 colored image and output a single classification value. In fact, there are many great pretrained CNN’s out in the field that only require minimum hyperparameter tuning to get great results. Since the goal for this project was not to only get great results, but to have a deeper understanding of how CNN’s work we created a CNN somewhat from the ground. 

In this paper we try to give a thorough discussion of the theoretical background of Convolutional Neural Networks. Then, we dive deeper into the algorithmic process of creating our CNN. Later, we discuss the overall process of exploring different models and testing different hyperparameter before settling on a final model. Then we try to understand possible explanations of the driving factors of what our results are telling us. Lastly, we conclude with some suggestions of other factors to consider to better train our model.

# Final Results 
Our baseline model was choosing the most frequent class. This happened to be our dandelions which would give us a 24% accuracy. Also, I implemented the data into a SVM with no blows or whistles and got an accuracy of 25.5%. We improved significantly from this baseline to getting an accuracy of 75.3% and a .74 loss value on our test set with our final neural net model. 
In the end our final model had the following features: 

	Input: 100×100×3 colored flower image
	Convolutional Layers: 4 where each had a (3,3) filter with RELU activation.
	Maxpooling Layers: 4 with (2,2) filter where each maxpooling layer followed a convolutional layer
	Dense Layers: 2 with RELU activation
	Last layer contains Softmax activation
	Nodes for each layer: 64
	Loss Function: Categorical Cross Entropy 
	Learning Rate Optimizer: Adam Optimizer with initial learning rate of .001
	Epochs: 25
	Dropout Rate: 20% after dense layer
	Image Augmentation 
	Total parameters: 182,661
  
I chose convolution layer, maxpooling layers, dense layers, and nodes based off of the analysis in the section above. Epochs decision was based off of the capacity of my computer. Dropout rate was based off what seems to be the standard dropout rate. I implemented data augmentation because of our limited dataset size for a neural network. I chose (3,3) filters and (2,2) filters for convolutional layers and maxpooling layers respectively based on what seemed to be standard. I chose RELU based off of the research that has been shown that RELU works well with neural nets. I chose Adam optimizer for our learning rate because it has been proven to be a better optimizer usually compared to others. I arbitrarily chose image input size based on whether I could see the details in the image. 

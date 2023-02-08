# Introducing Autodecompose: A novel architecture to decompose data to semantically independent properties.

![](https://github.com/rezabonyadi/autodecompose/blob/main/assets/20_people_voice_recog.gif)


Autodecompose is a self-supervised generative approach which guarantees establishing an embedding space that encodes semantically meaningful and relevant features for a given classification task. For a given task, our approach requires two augmentations to be designed: One that randomly alters all "properties" in the raw data except the one that is desired to be used for classification, and another that maintains all properties in the data while randomly alters the one that is desired to be used for classification. For example, for decomposing audio signals to sound source and content, you need to build an augmentation that alters the sound source while maintains the content, and another augmentation that alters the content while maintains the sound source (see the paper and the code where these two augmentations have been already built). These variations are fed into two separate encoders, and the output of the encoders are concatenated and used for reconstructing the original input. 

This is autodecompose applied to audio signals uttered by 30 different speakers (each color is one speaker). Note that no labels were given to the model and it is being trained completely self-supervised.


This is how the overall architecture of the autodecompose looks like.
<img src="https://user-images.githubusercontent.com/25924343/214697989-59c7a20e-4f7d-4a59-8c41-d056fa2519c5.png"  width="600" height="600">


The model can be applied to other tasks as long as the two mentioned augmentations can be designed. In other words, rather than labeling, one can implement these complementary augmentations, which could potentially be less labor intensive.


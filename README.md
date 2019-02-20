# My Suggestions and Learning materials for Deep Learning concepts
Hello Everyone,

I am Chandrasekar Sivaraman, I am currently learning basics concepts of deep learning which would enable me to implement a gesture recognition system. I am making this write up as a process to record my observations and also with the hope that it could serve as a platform for me to share my learnings to help people who are taking their first steps into the world of deep learning.

This repo is a collection of scripts that I have made in an attempt to better understand some underlying concepts of deep learning. I will mention all the major sources that I have used which I personally found to be the most effective in shaping my understanding of the important concepts.

I would like to link my other pages here which you could read to understand the concepts further :

 *[My Understanding of CNNs](https://iamanemic.github.io/cnn_basics/)
  
 *[Python Script to Visualize the Features Extracted by a CNN Filter](https://iamanemic.github.io/cnn_filter_visualization/)
  



Starting Point(just a suggestion) : I would first recommend to begin with the deep learning course on coursera by Andrew .N.G This would cover all the basics which you require.

Assuming that you have some understanding of a basic neuron and a single neuron network, The next step would be to try implementing a neural network on your own using just basic libraries. This following blog by adam trask will be very helpful to you in this regard: [https://iamtrask.github.io/2015/07/12/basic-python-network/](https://iamtrask.github.io/2015/07/12/basic-python-network/)

Convolutional Neural Networks (CNNs) was the biggest factor in plummetting the research in the field of deep learning. Even though CNNs were first successfully implemented by Yan Le Cun in the 90s for hand digit recognition, the CNNs became popular only in 2012(built by Alex Krizhevsky and team) convincingly beat all the previous models used in the ImageNet competition by dropping the classification error from 26% to 15%. If you are one of those nerds who likes to read research papers, here is a list of papers of historic importance in the field of deep learning in the chronological order. [https://docs.google.com/spreadsheets/d/1kZqCg5qS9MM4LoEHfIb2fLgf4IymXGOyXC9MBPSatuA/edit#gid=0](https://docs.google.com/spreadsheets/d/1kZqCg5qS9MM4LoEHfIb2fLgf4IymXGOyXC9MBPSatuA/edit#gid=0)

I would also highly recommend reading through the materials in this course on CNN: [http://cs231n.github.io/](http://cs231n.github.io/)


# Summary of a Basic Neural Network

If you don't overthink what a neural network is doing, It is just a sequence of matrix multiplications which result in 
matrices which are sent through a non-linearity function such as relu or sigmoid.

### why use non-linearity functions?
If you think about it, using numerous matrix multiplications is a series of linear operations. Lets say you have 5 different classes of images, if you are using linear operations you end up drawing straight lines or hyperplanes separating the 5 classes. This is not what you want, The very purpose of a neural network is to differentiate classes which aren't linearly separable. I hope this makes sense as to why we introduce a non-linearity after every set of matrix multiplications.

### What are neurons?
The neurons are nothing but values stored in matrices. These matrices are multiplied by the input or the matrix of neurons
that precedes it and the output is sent throuhg a non-linearity and the same process is repeated until you reach the output
matrix which predicts your output for the given input which was propagated through the neuron matrices. 

So, What now? The matrices were multiplied and the output was predicted as a probability. Was the predicted output correct?
How good or bad was your prediction? Based on these questions the neural network would try to adjust its weights in order to 
make its prediction better. 

### Why adjust its weights?

Well the weights are matrix values, The only thing a neural network actually does is matrix multiplications. So, does it now make sense that it should adjust its weights in order to adjust its predictions?

### So how does it adjust its weights?
Let me start with an analogy. Let us consider a football team consisting of 11 on field players and the potential substitutes on the bench and a coach/manager making the decisions. The outcome of the team after 90 mins of play is whether they won the game or the lost the game. It is as simple as that. If you consider what are the factors that affect that particular outcome, we could take a million parameters, but let us consider the players and the coach. Let us assume that defense was weak which led the team to lose the game, and in particular 2 of the defenders underperformed. Also, let us consider that everyone else perormed well(for simplicity). What is it that we have to change in order to win the next game?
Simple isnt it? we either replace the two under performing defenders or we invest more in their training regime so that they perform better in the upcoming game. So each player contributes to the outcome in either a positive or negetive way. 

Lets now go back to our weights. Assume that each weight value is a player that contributes the final outcome of the network. 
Each of the weight values have an error associated with the outcome. 
The network calculates the output predicted value using the current weights, this process is known as forward propagation. 
It would then calculate the errors associated with each weights depending on the difference between the actual and predicted output. The weights are then updated in a process called back propagation to have a reduced error towards the prediction.

This whole process when repeated a lot of times until the network and weights are all confident in their values towards making the prediction on a new data is called "training the network".




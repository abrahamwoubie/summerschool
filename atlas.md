---
layout: default
title: RNASeq | MLABST'17
---

# IMAGING DATA - Allen Brain Atlas

## Background reading
http://www.nature.com/nbt/journal/v33/n5/abs/nbt.3209.html

## Data
Allen Brain Atlas http://www.brain-map.org 

## Proposed solution

### Option 1

You could study this example approach proposed in mouse image study with CNN as a starting point: https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-015-0553-9 
and try to adapt this to human brain atlas, i.e. you would need to demonstrate that you can annotate gene expression patterns with human data.
To download images we have so far tested only one-by-one retrieval (you would need to find out if downloading all is even possible!), check instructions in:
http://help.brain-map.org/display/api/Downloading+an+Image
you need to find the desired imageIDs. 

- Do any search in http://human.brain-map.org/ish/search
- Click a SpecimenID in the search results
- Click the experiment ID in the "Selection Information"-box
- There is a small button in the top right corner of the image. Howering the mouse over it displays a text "Launch a high resolution viewer in a new window". Click it.
- You can either download the images here using the download button or asinstructed in:
http://help.brain-map.org/display/api/Downloading+an+Image
and download the image using the imageId shown in the web address of this window.
- For every ISH-image there is an image showing gene expression areas and a Nissil-reference image of the shown area. Those images can also be viewed in this window.
Properties of search interface are explained here  http://human.brain-map.org/ish/search 
 
The next step (which you can complete even w/o image data) is to critically evaluate the example approach proposed in mouse image study with CNN: https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-015-0553-9 
To get it up and running for doing some tests, here some hints:
- VLFeat can be used via Matlab: http://www.vlfeat.org/install-matlab.html
- SIFT-algorithm to extract feature vectors. User guide: http://www.vlfeat.org/overview/sift.html
- Bag-of-words model generated from the image using random sampling + obtained feature vectors ->  K-means-algorithm -> visual codebook
- The OverFeat-neural network structure and source code is available in github ( https://github.com/sermanet/OverFeat ). It comes with python and torch APIs.
- The model comes with pre-trained weights.
- Example of the usage ( https://github.com/sermanet/OverFeat/blob/master/API/python/sample.py )
- The OverFeat-model's input need to be resized or cropped to 231x231 and when using python it needs to be given to the model in a numpy array with dtype=numpy.float32 in the shape of 3xHxW (RGB image with size HxW). Images with the size HxWx3 can be transposed to desired shape.

Option 2
Implement your own network model, motivated by earlier literature and what you learned so far. Here you would also need to describe how to obtain training and test data (but if your focus is on method development, we will not require so much time spent getting the data, unless you aim for the leader board where we will give higher rank to full solutions)
- For gene localization check above instructions for Specimen section's expression images (ground truth)
- Implement network e.g. in python using keras with tensorflow. You can make something like the OverFeat model's architechture (Figure 2 in https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-015-0553-9 ) or implement your own.
- Possible tricky parts: shape of tissue sections varies and also location where section was cut from. You might need to normalize your data somehow. You should propose some solutions here.
- Compared to Nissil-reference images some of the Allen Brain Atlas images are very dim -> you may need to smooth the color data. Again, propose some solutions here.

To get a good rank on the leaderboard, you should benchmark your solution with simulations and/or real data. 

### Evaluation

clever choice of methodology
clever use of data
demonstrating preliminary success, minimum requirement is that your approach is able to detect neuronal loss in AD

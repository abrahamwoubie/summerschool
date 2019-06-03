---
layout: default
title: Tasks | MLABST'17
---

{% include buttons.html %}

### Return submissions on Moodle: [https://moodle.uef.fi/course/view.php?id=17032](https://moodle.uef.fi/course/view.php?id=17032)

## Learning diary
Deadline: 10.9.2017, 11:55pm<br>
Returnables: Filled learning diary (questions answered) <br>
Filled learning diary will be returned to the Moodle (link will be added later).

For the first week of the course, participants are required to submit filled
learning diary that consists of different questions related to given lectures. 

You can find the learning diary on "Course Notes" section. Current version 
on the site is the final version.

## Project (done during second week, 21.8 - 25.8, and onward)
Deadline: 10.9.2017, 11:55pm<br>
Returnables: Final report and source code <br>
Report and source code will be returned to the Moodle (link will be added later).

Second week will consist of working on a pre-defined project/task, writing a
report with theory, methodology, experiment setup and final results as well as returning source code produced. 

There will be tutoring sessions on the second week of the summer school where
TA's will be answering and assisting you with your projects. There will also be 
an IRC chat (see "Chat" tab, available during second week) where you can ask questions outside tutoring sessions. 

*Note from TAs: We are not top-experts in these areas and the tasks are quite fresh/new/open problems. As such, do not expect pre-made solutions or 100% correct suggestions from us :)*

**Note: Accessing required datasets requires certified Synapse account. See "Dataset" page**

Projects can be one of the following (one per person): 

- Single Cell RNA-sequencing (scRNAseq)
    - [Check more information here]({{ site.url }}/{{ site.baseurl }}/content/biotasks.pdf)
    - The aim is to predicttheproportion of different cell types from bulk RNASeq using clever approach utilizing data from single cell RNASeq -> cell type deconvolution problem
    - Challenge: Can you come up with a clever way to utilize scRNAseq to deconvolve the signal in the Alzheimer brain tissue samples?
- Allen Brain Atlas in situ hybridization
    - [Check more information here]({{ site.url }}/{{ site.baseurl }}/content/biotasks.pdf)
    - The aim is to perform automated image annotation to find out which cell types/tissue substructures express the genes that change their level in Alzheimer’s disease patients (RNA-seq profiles)
    - Challenge: Can you come up with a clever way to utilize Allen Brain Atlas data to link the gene expression changes in the Alzheimer brain to specific brain regions?
- Detecting Parkinson's Disease (PD) using speech data
    - [Synapse page](https://www.synapse.org/#!Synapse:syn4993293/wiki/)
    - Task is to use speech data ‘/aaaa/’ sound to predict whether speaker has PD or not. 
    - Speakers used iphone app to self collect the data. Large number of speakers and samples are available (> 50k samples). 
    - We will pre-select samples for training, validation and test sets. We will give the baseline performance on the test set and hope is that students will come up with novel ideas which exceed the baseline performance. 
    - Finally, the interesting thing is to see what features in the speech are predictive of the PD. This can lead to new biology and possibly practical diagnostic tools.
    - **Note: This data requires *validated* Synapse account, which requires signed letters from your institute ( [Check Steps 3-5  here](https://www.synapse.org/#!Synapse:syn4993293/wiki/247860) )**

### Final report structure

Final report should be a single PDF file (text document). There are no limitation/requirements for the length, but we expect detailed explanation.
A good report should include following:

- Introduction to the dataset/task, possibly describing why the task is difficult (if it indeed is)
- Explanation of the methodology/approach used to solve the task. E.g. Algorithms/Methods/Models used, the pipeline
- Implementation details / experiment setup. E.g. Hyperparameters used, number of samples from different classes, etc.
- Evaluation of the results and discussion of the project. E.g. Accuracy of the classification, what could be improved, what was observed.

    
### Getting started with Python

- Install [Python](https://www.python.org/) (3.6 preferred) or [Anaconda](https://www.continuum.io/) (or [Miniconda](https://conda.io/miniconda.html) )
    - Note that some Linux distributions already have Python pre-installed, e.g. Ubuntu 16.04 has Python 3.5
- For developing code, install IDE of your choice. E.g: Geany, PyCharm (heavy-ish), Notepad++
- You will likely need some extra libraries that do not come with Python:
    - On Linux/OSX these can be often installed with simple `pip3 install [library name]`
    - On Windows, often pre-built packages are needed. You can find up-to-date pre-compiled libraries here: [http://www.lfd.uci.edu/~gohlke/pythonlibs/](http://www.lfd.uci.edu/~gohlke/pythonlibs/)
        - To install a library: Download the .whl file, navigate to [Python install dir]/Scripts with command line and command `pip install [.whl file]`
- You can use pb.csc.fi jupyter notebooks for prototyping. **Note that files will be deleted after set time (e.g. 8h)on pb.csc.fi notebooks!**
- Develope and test your implementation on local machine with smaller dataset, if full dataset/training is too heavy.
- If more computing resources are required, try using CSC Taito/Taito-GPU. [See this Github repo for some tutorials on running python script on Taito](https://github.com/CSCfi/machine-learning-scripts/tree/master/courses/uefml2017)

- List of some libraries you will probably need / could use:
    - NumPy (basic math functions)
    - Scipy (misc math functions)
    - scikit-learn (machine learning)
    - TensorFlow (deep learning)
    - Keras (deep learning)
    - matplotlib (plotting)
    - librosa (audio processing)
    - sidekit (audio processing, used for evaluation in PD task)

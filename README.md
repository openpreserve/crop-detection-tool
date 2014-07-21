Cropdet Installation & Use
============================
*The cropping error detection tool*

Installation Guide
------------------

### Requirements

To install you need:

* Python 2.7
* Python libraries numpy, matplotlib, pylab, PIL e.g. install pythonXY
* Git
* PyScripter editor can support you by project configuration

### Download

| Version | Size   | SHA1                                                    |                      |
|---------|--------|---------------------------------------------------------|----------------------|
| v1.0    | 23.6 MB| <small>1b34d11f66fe4b847f271a5aaaabb02c7917690c</small> |[download](https://github.com/openplanets/cropdet/archive/master.zip)            |

### Installing Cropdet

#### Use PyScripter or command line to execute Python project from github sources.
1. Check out project sources from github e.g. using TortoiseGit
2. Install necessary Python libraries e.g. pythonXY

Using Cropdet
--------------

Execute the main Python script 'croppingDetection.py'  

The folder 'samples' should be in root directory.

### Basic Workflows

#### Cropping Error Detection

The cropping error detection algorithm is summarized as follows:

The user triggers a complete collection analysis, the results of which are stored in a text file. 
In order to detect documents with cropping error we aggregate digital text document specific expert knowledge and analyse images using image profiling technique. 
In the first workflow step the image is loaded in RGB colour format. In the next step RGB image is converted to the greyscale format using the perceptually weighted formula (see Guojun (1998)). 
We used formula (1):

Pres = 0,299 x Pred + 0,587 x Pgreen + 0,114 x Pblue   (1)

Where Pres is a pixel value in a greyscale image, Pred, Pgreen and Pblue are pixel values in an RGB image.

In subsequent steps we analyse greyscale image and calculate left and right border distances in order to apply different parameters like minimal and maximal border distance, 
left to right border relation and average luminance (Pres value) for the image. Additionally the average luminance for the whole collection can be calculated and used as a 
parameter in the analysis. The evaluated average luminance values for X axis demonstrate calculated values visually. This supports the human expert to infer an informed 
evaluation of the cropping quality of image candidates that could be mis-cropped and evaluate whether these images are in fact affected by the indicated error and to 
perform necessary actions.  

The presented tool is working on a greyscale representation of the image data and is configured with relative measures. 
The initial configurations should be set by a digital preservation expert who is familiar with the material of a particular institution and the type of document collection.

Command line use
----------------

### Sample usage

	croppingDetection.py

### Output of cropping error detection script is a list of possible candidates 

E.g. collection contains 1 document. The document 00000496_1.jpg from the folder 'samples' has size 1344053 bytes and contains cropping error.
Result of analysis is a presentation of the analyzed image and its luminance projection with estimation whether this scan contains error.
In this way the user is able to draw a conclusion as to whether a cropping error candidate image is actually an error.

rand 3
path  samples\
****** name:  00000496_1.jpg , size 1344053
2366 3581
Total calculation time:  18.0158903679

## Features and roadmap

### Version 1.0

* Cropping error detection in a digital document collection



